# CDXGIOutput::WaitForVBlank(void)

- ea: `0x180035200`
- end: `0x180035339`
- name: `?WaitForVBlank@CDXGIOutput@@UEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(CDXGIOutput *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180035200`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800352c6`
- `ntdll!EtwEventWrite` at `0x18003532e`
- `ntdll!EtwEventWrite` at `0x1800352c6`
- `ntdll!EtwEventWrite` at `0x18003532e`

## pseudocode

```c
__int64 __fastcall CDXGIOutput::WaitForVBlank(CDXGIOutput *this)
{
  int v2; // eax
  char v4; // [rsp+20h] [rbp-48h]
  int v5; // [rsp+24h] [rbp-44h] BYREF
  CDXGIOutput *v6; // [rsp+28h] [rbp-40h] BYREF
  __int64 v7; // [rsp+30h] [rbp-38h] BYREF
  int v8; // [rsp+38h] [rbp-30h]
  CDXGIOutput **v9; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h]

  v6 = this;
  v4 = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v9 = &v6;
    v4 = 1;
    v10 = 8;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGIOutput_WaitForVBlank_Start, 1, &v9);
  }
  v7 = 0;
  v8 = 0;
  v2 = *((_DWORD *)this + 109);
  if ( !v2 )
    v2 = *(_DWORD *)(*((_QWORD *)this + 21) + 220LL);
  LODWORD(v7) = v2;
  v8 = *((_DWORD *)this + 64);
  (*(void (__fastcall **)(__int64 *))(*((_QWORD *)this + 21) + 328LL))(&v7);
  v5 = 0;
  if ( v4 )
  {
    v9 = (CDXGIOutput **)&v5;
    v10 = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGIOutput_WaitForVBlank_Stop, 1, &v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180035200  mov     [rsp+arg_8], rbx
0x180035205  push    rdi
0x180035206  sub     rsp, 60h
0x18003520a  mov     rax, cs:__security_cookie
0x180035211  xor     rax, rsp
0x180035214  mov     [rsp+68h+var_18], rax
0x180035219  xor     edi, edi
0x18003521b  mov     [rsp+68h+var_40], rcx
0x180035220  cmp     cs:dword_180108134, edi
0x180035226  mov     rbx, rcx
0x180035229  mov     [rsp+68h+var_48], 0
0x18003522e  jz      short loc_180035247
0x180035230  mov     rdx, 4000000000000000h
0x18003523a  test    cs:qword_180108120, rdx
0x180035241  jnz     loc_1800352E6
0x180035247  xor     eax, eax
0x180035249  mov     [rsp+68h+var_38], rax
0x18003524e  mov     [rsp+68h+var_30], eax
0x180035252  mov     eax, [rbx+1B4h]
0x180035258  test    eax, eax
0x18003525a  jnz     short loc_180035269
0x18003525c  mov     rax, [rbx+0A8h]
0x180035263  mov     eax, [rax+0DCh]
0x180035269  mov     dword ptr [rsp+68h+var_38], eax
0x18003526d  lea     rcx, [rsp+68h+var_38]
0x180035272  mov     eax, [rbx+100h]
0x180035278  mov     [rsp+68h+var_30], eax
0x18003527c  mov     rax, [rbx+0A8h]
0x180035283  mov     rax, [rax+148h]
0x18003528a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003528f  mov     [rsp+68h+var_44], edi
0x180035293  cmp     [rsp+68h+var_48], dil
0x180035298  jz      short loc_1800352CC
0x18003529a  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800352a1  lea     rax, [rsp+68h+var_44]
0x1800352a6  lea     r9, [rsp+68h+var_28]
0x1800352ab  mov     [rsp+68h+var_28], rax
0x1800352b0  mov     r8d, 1
0x1800352b6  mov     [rsp+68h+var_20], 4
0x1800352bf  lea     rdx, IDXGIOutput_WaitForVBlank_Stop
0x1800352c6  call    cs:__imp_EtwEventWrite
0x1800352cc  xor     eax, eax
0x1800352ce  mov     rcx, [rsp+68h+var_18]
0x1800352d3  xor     rcx, rsp; StackCookie
0x1800352d6  call    __security_check_cookie
0x1800352db  mov     rbx, [rsp+68h+arg_8]
0x1800352e0  add     rsp, 60h
0x1800352e4  pop     rdi
0x1800352e5  retn
0x1800352e6  mov     rax, cs:qword_180108128
0x1800352ed  and     rax, rdx
0x1800352f0  cmp     rax, cs:qword_180108128
0x1800352f7  jnz     loc_180035247
0x1800352fd  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180035304  lea     rax, [rsp+68h+var_40]
0x180035309  lea     r9, [rsp+68h+var_28]
0x18003530e  mov     [rsp+68h+var_28], rax
0x180035313  mov     r8d, 1
0x180035319  mov     [rsp+68h+var_48], 1
0x18003531e  lea     rdx, IDXGIOutput_WaitForVBlank_Start
0x180035325  mov     [rsp+68h+var_20], 8
0x18003532e  call    cs:__imp_EtwEventWrite
0x180035334  jmp     loc_180035247
```
