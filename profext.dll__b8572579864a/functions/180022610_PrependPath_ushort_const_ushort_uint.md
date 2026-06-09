# PrependPath(ushort const *,ushort *,uint)

- ea: `0x180022610`
- end: `0x1800226e2`
- name: `?PrependPath@@YAHPEBGPEAGI@Z`
- size: `210`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010810`

## callees

- `0x180006400`
- `0x180010384`
- `0x18002257c`
- `0x180022610`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180022671`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180022671`

## pseudocode

```c
__int64 __fastcall PrependPath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // r8d
  const char *v5; // r9
  LPWSTR FilePart; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  FilePart = 0;
  if ( a1 && *a1 )
  {
    if ( SearchPathW(0, a1, L".exe", 0x104u, Buffer, &FilePart) )
    {
      UnExpandSysRoot(Buffer, a2);
    }
    else
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x3D6, v4, v5);
      StringCchCopyW(a2, 0x104u, a1);
    }
  }
  else
  {
    *a2 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180022610  mov     [rsp+arg_10], rbx
0x180022615  mov     [rsp+arg_18], rsi
0x18002261a  push    rdi
0x18002261b  sub     rsp, 260h
0x180022622  mov     rax, cs:__security_cookie
0x180022629  xor     rax, rsp
0x18002262c  mov     [rsp+268h+var_18], rax
0x180022634  xor     esi, esi
0x180022636  mov     rdi, rdx
0x180022639  mov     [rsp+268h+FilePart], rsi
0x18002263e  mov     rbx, rcx
0x180022641  test    rcx, rcx
0x180022644  jz      short loc_1800226B4
0x180022646  cmp     [rcx], si
0x180022649  jz      short loc_1800226B4
0x18002264b  lea     rax, [rsp+268h+FilePart]
0x180022650  mov     rdx, rcx; lpFileName
0x180022653  mov     [rsp+268h+lpFilePart], rax; lpFilePart
0x180022658  lea     r8, Extension; ".exe"
0x18002265f  lea     rax, [rsp+268h+Buffer]
0x180022664  mov     r9d, 104h; nBufferLength
0x18002266a  xor     ecx, ecx; lpPath
0x18002266c  mov     [rsp+268h+lpBuffer], rax; lpBuffer
0x180022671  call    cs:__imp_SearchPathW
0x180022678  nop     dword ptr [rax+rax+00h]
0x18002267d  test    eax, eax
0x18002267f  jnz     short loc_1800226A5
0x180022681  mov     rcx, [rsp+268h]; this
0x180022689  mov     edx, 3D6h; void *
0x18002268e  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180022693  mov     r8, rbx; unsigned __int16 *
0x180022696  mov     edx, 104h; unsigned __int64
0x18002269b  mov     rcx, rdi; unsigned __int16 *
0x18002269e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800226a3  jmp     short loc_1800226B7
0x1800226a5  mov     rdx, rdi; unsigned __int16 *
0x1800226a8  lea     rcx, [rsp+268h+Buffer]; unsigned __int16 *
0x1800226ad  call    ?UnExpandSysRoot@@YAHPEBGPEAGK@Z; UnExpandSysRoot(ushort const *,ushort *,ulong)
0x1800226b2  jmp     short loc_1800226B7
0x1800226b4  mov     [rdx], si
0x1800226b7  mov     eax, 1
0x1800226bc  mov     rcx, [rsp+268h+var_18]
0x1800226c4  xor     rcx, rsp; StackCookie
0x1800226c7  call    __security_check_cookie
0x1800226cc  lea     r11, [rsp+268h+var_8]
0x1800226d4  mov     rbx, [r11+20h]
0x1800226d8  mov     rsi, [r11+28h]
0x1800226dc  mov     rsp, r11
0x1800226df  pop     rdi
0x1800226e0  retn
```
