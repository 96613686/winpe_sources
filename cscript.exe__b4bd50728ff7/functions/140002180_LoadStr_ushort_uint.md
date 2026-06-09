# LoadStr(ushort * *,uint)

- ea: `0x140002180`
- end: `0x14000224f`
- name: `?LoadStr@@YAHPEAPEAGI@Z`
- size: `207`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140001330`
- `0x140001bd0`
- `0x1400046bc`
- `0x14000a120`
- `0x14000a200`
- `0x14000d2e0`
- `0x14000f988`
- `0x140012f20`

## callees

- `0x140002180`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000221e`
- `OLEAUT32!__imp_SysAllocString` at `0x14000221e`
- `KERNEL32!MultiByteToWideChar` at `0x14000220a`
- `KERNEL32!MultiByteToWideChar` at `0x14000220a`
- `USER32!LoadStringW` at `0x1400021cd`
- `USER32!LoadStringW` at `0x1400021cd`
- `USER32!LoadStringA` at `0x1400021dc`
- `USER32!LoadStringA` at `0x1400021dc`

## pseudocode

```c
unsigned __int16 *__fastcall LoadStr(unsigned __int16 **a1, UINT a2)
{
  bool v2; // zf
  int StringW; // eax
  unsigned int v5; // ebx
  unsigned __int16 *result; // rax
  CHAR MultiByteStr[2048]; // [rsp+30h] [rbp-1818h] BYREF
  WCHAR Buffer[2048]; // [rsp+830h] [rbp-1018h] BYREF

  v2 = !Global::g_fWindowsNT;
  *a1 = 0;
  if ( v2 )
  {
    v5 = 0;
    if ( !LoadStringA(Global::g_hResource, a2, MultiByteStr, 2048) )
      return (unsigned __int16 *)v5;
    StringW = MultiByteToWideChar(0, 0, MultiByteStr, -1, Buffer, 2048);
  }
  else
  {
    StringW = LoadStringW(Global::g_hResource, a2, Buffer, 2048);
  }
  v5 = StringW;
  if ( !StringW )
    return (unsigned __int16 *)v5;
  result = SysAllocString(Buffer);
  *a1 = result;
  if ( result )
    return (unsigned __int16 *)v5;
  return result;
}

```

## disassembly

```asm
0x140002180  mov     [rsp+arg_10], rbx
0x140002185  push    rdi
0x140002186  mov     eax, 1840h
0x14000218b  call    _alloca_probe
0x140002190  sub     rsp, rax
0x140002193  mov     rax, cs:__security_cookie
0x14000219a  xor     rax, rsp
0x14000219d  mov     [rsp+1848h+var_18], rax
0x1400021a5  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x1400021ac  mov     rdi, rcx
0x1400021af  mov     qword ptr [rcx], 0
0x1400021b6  mov     r9d, 800h; cchBufferMax
0x1400021bc  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1400021c3  jz      short loc_1400021D5
0x1400021c5  lea     r8, [rsp+1848h+Buffer]; lpBuffer
0x1400021cd  call    cs:__imp_LoadStringW
0x1400021d3  jmp     short loc_140002210
0x1400021d5  lea     r8, [rsp+1848h+MultiByteStr]; lpBuffer
0x1400021da  xor     ebx, ebx
0x1400021dc  call    cs:__imp_LoadStringA
0x1400021e2  test    eax, eax
0x1400021e4  jz      short loc_14000222C
0x1400021e6  lea     rax, [rsp+1848h+Buffer]
0x1400021ee  mov     [rsp+1848h+cchWideChar], 800h; cchWideChar
0x1400021f6  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1400021fc  mov     [rsp+1848h+lpWideCharStr], rax; lpWideCharStr
0x140002201  lea     r8, [rsp+1848h+MultiByteStr]; lpMultiByteStr
0x140002206  xor     edx, edx; dwFlags
0x140002208  xor     ecx, ecx; CodePage
0x14000220a  call    cs:__imp_MultiByteToWideChar
0x140002210  mov     ebx, eax
0x140002212  test    eax, eax
0x140002214  jz      short loc_14000222C
0x140002216  lea     rcx, [rsp+1848h+Buffer]; psz
0x14000221e  call    cs:__imp_SysAllocString
0x140002224  mov     [rdi], rax
0x140002227  test    rax, rax
0x14000222a  jz      short loc_14000222E
0x14000222c  mov     eax, ebx
0x14000222e  mov     rcx, [rsp+1848h+var_18]
0x140002236  xor     rcx, rsp; StackCookie
0x140002239  call    __security_check_cookie
0x14000223e  mov     rbx, [rsp+1848h+arg_10]
0x140002246  add     rsp, 1840h
0x14000224d  pop     rdi
0x14000224e  retn
```
