# PowerShellClrWorker::LoadWorkerCallbackPtrs(_PwrshPluginWkr_Ptrs *,ushort *,PlugInException * *)

- ea: `0x180005ba0`
- end: `0x180005e68`
- name: `?LoadWorkerCallbackPtrs@PowerShellClrWorker@@UEAAIPEAU_PwrshPluginWkr_Ptrs@@PEAGPEAPEAVPlugInException@@@Z`
- size: `712`
- prototype: `__int64 __fastcall(PowerShellClrWorker *this, struct _PwrshPluginWkr_Ptrs *, unsigned __int16 *, struct PlugInException **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x180001098`
- `0x180001318`
- `0x180002e80`
- `0x180005ba0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005cb8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005cb8`
- `KERNEL32!FormatMessageW` at `0x180005c2e`
- `KERNEL32!FormatMessageW` at `0x180005c2e`
- `KERNEL32!LocalFree` at `0x180005cc6`
- `KERNEL32!LocalFree` at `0x180005cc6`
- `KERNEL32!GetLastError` at `0x180005c07`
- `KERNEL32!GetLastError` at `0x180005c07`

## pseudocode

```c
__int64 __fastcall PowerShellClrWorker::LoadWorkerCallbackPtrs(
        PowerShellClrWorker *this,
        struct _PwrshPluginWkr_Ptrs *a2,
        unsigned __int16 *a3,
        struct PlugInException **a4)
{
  _QWORD *v4; // rdi
  _QWORD *v6; // rbx
  void *v9; // rdi
  DWORD LastError; // eax
  DWORD v11; // eax
  unsigned __int64 v12; // rbx
  _WORD *v13; // rax
  unsigned __int16 *v14; // rdx
  __int64 v15; // rcx
  _WORD *v16; // rcx
  unsigned __int16 *v17; // rax
  void (*v19)(void); // r15
  struct PlugInException *v20; // rax
  unsigned __int16 *Buffer; // [rsp+70h] [rbp+8h] BYREF
  struct PlugInException *v22; // [rsp+80h] [rbp+18h]

  v4 = (_QWORD *)((char *)this + 136);
  *a4 = 0;
  v6 = (_QWORD *)((char *)this + 16);
  if ( a3 )
    *v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)*v4 + 8LL))(*v4, a3, 0, 0);
  if ( !*v6 )
  {
    v9 = 0;
    Buffer = 0;
    LastError = GetLastError();
    v11 = FormatMessageW(0x1100u, 0, LastError, 0, (LPWSTR)&Buffer, 0, 0);
    if ( !v11 )
    {
LABEL_18:
      v17 = (unsigned __int16 *)operator new(0x10u);
      Buffer = v17;
      if ( v17 )
      {
        *(_DWORD *)v17 = 1104;
        *((_QWORD *)v17 + 1) = v9;
      }
      else
      {
        v17 = 0;
      }
      *a4 = (struct PlugInException *)v17;
      return 1104;
    }
    v12 = v11 + 1;
    v13 = operator new[](saturated_mul(v12, 2u));
    v9 = v13;
    if ( v13 )
    {
      if ( v12 )
      {
        if ( v12 <= 0x7FFFFFFF )
        {
          v14 = Buffer;
          v15 = 2147483646;
          do
          {
            if ( !v15 )
              break;
            if ( !*v14 )
              break;
            *v13++ = *v14++;
            --v15;
            --v12;
          }
          while ( v12 );
          v16 = v13 - 1;
          if ( v12 )
            v16 = v13;
          *v16 = 0;
          if ( v12 )
            goto LABEL_17;
        }
        else
        {
          *v13 = 0;
        }
      }
      operator delete[](v9);
      v9 = 0;
    }
LABEL_17:
    LocalFree(Buffer);
    goto LABEL_18;
  }
  v19 = (void (*)(void))(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 7));
  *(_QWORD *)a2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                    *v4,
                    *v6,
                    *((_QWORD *)this + 8));
  *((_QWORD *)a2 + 1) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 9));
  *((_QWORD *)a2 + 2) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 10));
  *((_QWORD *)a2 + 3) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 11));
  *((_QWORD *)a2 + 4) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 12));
  *((_QWORD *)a2 + 5) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 13));
  *((_QWORD *)a2 + 6) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 14));
  *((_QWORD *)a2 + 7) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 15));
  *((_QWORD *)a2 + 8) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(
                          *v4,
                          *v6,
                          *((_QWORD *)this + 16));
  if ( v19 )
  {
    v19();
    return 0;
  }
  else
  {
    Buffer = 0;
    GetFormattedErrorMessage(&Buffer, 0x805403EB);
    v20 = (struct PlugInException *)operator new(0x10u);
    v22 = v20;
    if ( v20 )
    {
      *((_QWORD *)v20 + 1) = Buffer;
      *(_DWORD *)v20 = -2141977621;
    }
    else
    {
      v20 = 0;
    }
    *a4 = v20;
    return 2152989675LL;
  }
}

```

## disassembly

```asm
0x180005ba0  mov     [rsp+arg_8], rbx
0x180005ba5  mov     [rsp+arg_18], rbp
0x180005baa  push    rsi
0x180005bab  push    rdi
0x180005bac  push    r12
0x180005bae  push    r14
0x180005bb0  push    r15
0x180005bb2  sub     rsp, 40h
0x180005bb6  xor     r12d, r12d
0x180005bb9  lea     rdi, [rcx+88h]
0x180005bc0  mov     [r9], r12
0x180005bc3  mov     rsi, r9
0x180005bc6  lea     rbx, [rcx+10h]
0x180005bca  mov     r10, r8
0x180005bcd  mov     r14, rdx
0x180005bd0  mov     rbp, rcx
0x180005bd3  test    r8, r8
0x180005bd6  jz      short loc_180005BF3
0x180005bd8  mov     rcx, [rdi]
0x180005bdb  xor     r9d, r9d
0x180005bde  xor     r8d, r8d
0x180005be1  mov     rdx, r10
0x180005be4  mov     rax, [rcx]
0x180005be7  mov     rax, [rax+8]
0x180005beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf0  mov     [rbx], rax
0x180005bf3  mov     rdx, [rbx]
0x180005bf6  test    rdx, rdx
0x180005bf9  jnz     loc_180005CFA
0x180005bff  mov     rdi, r12
0x180005c02  mov     [rsp+68h+Buffer], r12
0x180005c07  call    cs:__imp_GetLastError
0x180005c0d  mov     [rsp+68h+Arguments], r12; Arguments
0x180005c12  xor     r9d, r9d; dwLanguageId
0x180005c15  mov     r8d, eax; dwMessageId
0x180005c18  mov     [rsp+68h+nSize], r12d; nSize
0x180005c1d  lea     rax, [rsp+68h+Buffer]
0x180005c22  xor     edx, edx; lpSource
0x180005c24  mov     ecx, 1100h; dwFlags
0x180005c29  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x180005c2e  call    cs:__imp_FormatMessageW
0x180005c34  test    eax, eax
0x180005c36  jz      loc_180005CCC
0x180005c3c  lea     ebx, [rax+1]
0x180005c3f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005c46  mov     eax, 2
0x180005c4b  mul     rbx
0x180005c4e  cmovb   rax, rcx
0x180005c52  mov     rcx, rax; unsigned __int64
0x180005c55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005c5a  mov     rdi, rax
0x180005c5d  test    rax, rax
0x180005c60  jz      short loc_180005CC1
0x180005c62  test    rbx, rbx
0x180005c65  jz      short loc_180005CB5
0x180005c67  cmp     rbx, 7FFFFFFFh
0x180005c6e  jbe     short loc_180005C76
0x180005c70  mov     [rax], r12w
0x180005c74  jmp     short loc_180005CB5
0x180005c76  mov     rdx, [rsp+68h+Buffer]
0x180005c7b  mov     ecx, 7FFFFFFEh
0x180005c80  test    rcx, rcx
0x180005c83  jz      short loc_180005CA4
0x180005c85  movzx   r8d, word ptr [rdx]
0x180005c89  test    r8w, r8w
0x180005c8d  jz      short loc_180005CA4
0x180005c8f  mov     [rax], r8w
0x180005c93  add     rdx, 2
0x180005c97  add     rax, 2
0x180005c9b  dec     rcx
0x180005c9e  sub     rbx, 1
0x180005ca2  jnz     short loc_180005C80
0x180005ca4  test    rbx, rbx
0x180005ca7  lea     rcx, [rax-2]
0x180005cab  cmovnz  rcx, rax
0x180005caf  mov     [rcx], r12w
0x180005cb3  jnz     short loc_180005CC1
0x180005cb5  mov     rcx, rdi
0x180005cb8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005cbe  mov     rdi, r12
0x180005cc1  mov     rcx, [rsp+68h+Buffer]; hMem
0x180005cc6  call    cs:__imp_LocalFree
0x180005ccc  mov     ecx, 10h; Size
0x180005cd1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cd6  mov     [rsp+68h+Buffer], rax
0x180005cdb  mov     ecx, 450h
0x180005ce0  test    rax, rax
0x180005ce3  jz      short loc_180005CED
0x180005ce5  mov     [rax], ecx
0x180005ce7  mov     [rax+8], rdi
0x180005ceb  jmp     short loc_180005CF0
0x180005ced  mov     rax, r12
0x180005cf0  mov     [rsi], rax
0x180005cf3  mov     eax, ecx
0x180005cf5  jmp     loc_180005E4F
0x180005cfa  mov     rcx, [rdi]
0x180005cfd  mov     r8, [rbp+38h]
0x180005d01  mov     rax, [rcx]
0x180005d04  mov     rax, [rax+28h]
0x180005d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d0d  mov     rcx, [rdi]
0x180005d10  mov     r15, rax
0x180005d13  mov     r8, [rbp+40h]
0x180005d17  mov     rdx, [rcx]
0x180005d1a  mov     rax, [rdx+28h]
0x180005d1e  mov     rdx, [rbx]
0x180005d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d26  mov     [r14], rax
0x180005d29  mov     rcx, [rdi]
0x180005d2c  mov     r8, [rbp+48h]
0x180005d30  mov     rdx, [rcx]
0x180005d33  mov     rax, [rdx+28h]
0x180005d37  mov     rdx, [rbx]
0x180005d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3f  mov     [r14+8], rax
0x180005d43  mov     rcx, [rdi]
0x180005d46  mov     r8, [rbp+50h]
0x180005d4a  mov     rdx, [rbx]
0x180005d4d  mov     rax, [rcx]
0x180005d50  mov     rax, [rax+28h]
0x180005d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d59  mov     [r14+10h], rax
0x180005d5d  mov     rcx, [rdi]
0x180005d60  mov     r8, [rbp+58h]
0x180005d64  mov     rdx, [rbx]
0x180005d67  mov     rax, [rcx]
0x180005d6a  mov     rax, [rax+28h]
0x180005d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d73  mov     [r14+18h], rax
0x180005d77  mov     rcx, [rdi]
0x180005d7a  mov     r8, [rbp+60h]
0x180005d7e  mov     rdx, [rbx]
0x180005d81  mov     rax, [rcx]
0x180005d84  mov     rax, [rax+28h]
0x180005d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d8d  mov     [r14+20h], rax
0x180005d91  mov     rcx, [rdi]
0x180005d94  mov     r8, [rbp+68h]
0x180005d98  mov     rdx, [rbx]
0x180005d9b  mov     rax, [rcx]
0x180005d9e  mov     rax, [rax+28h]
0x180005da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da7  mov     [r14+28h], rax
0x180005dab  mov     rcx, [rdi]
0x180005dae  mov     r8, [rbp+70h]
0x180005db2  mov     rdx, [rbx]
0x180005db5  mov     rax, [rcx]
0x180005db8  mov     rax, [rax+28h]
0x180005dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dc1  mov     [r14+30h], rax
0x180005dc5  mov     rcx, [rdi]
0x180005dc8  mov     r8, [rbp+78h]
0x180005dcc  mov     rdx, [rbx]
0x180005dcf  mov     rax, [rcx]
0x180005dd2  mov     rax, [rax+28h]
0x180005dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ddb  mov     [r14+38h], rax
0x180005ddf  mov     rcx, [rdi]
0x180005de2  mov     r8, [rbp+80h]
0x180005de9  mov     rdx, [rbx]
0x180005dec  mov     rax, [rcx]
0x180005def  mov     rax, [rax+28h]
0x180005df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df8  mov     [r14+40h], rax
0x180005dfc  test    r15, r15
0x180005dff  jz      short loc_180005E0D
0x180005e01  mov     rax, r15
0x180005e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e09  xor     eax, eax
0x180005e0b  jmp     short loc_180005E4F
0x180005e0d  mov     ebx, 805403EBh
0x180005e12  mov     [rsp+68h+Buffer], r12
0x180005e17  mov     edx, ebx; unsigned int
0x180005e19  lea     rcx, [rsp+68h+Buffer]; unsigned __int16 **
0x180005e1e  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180005e23  mov     ecx, 10h; Size
0x180005e28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e2d  mov     [rsp+68h+arg_10], rax
0x180005e35  test    rax, rax
0x180005e38  jz      short loc_180005E47
0x180005e3a  mov     rcx, [rsp+68h+Buffer]
0x180005e3f  mov     [rax+8], rcx
0x180005e43  mov     [rax], ebx
0x180005e45  jmp     short loc_180005E4A
0x180005e47  mov     rax, r12
0x180005e4a  mov     [rsi], rax
0x180005e4d  mov     eax, ebx
0x180005e4f  lea     r11, [rsp+68h+var_28]
0x180005e54  mov     rbx, [r11+38h]
0x180005e58  mov     rbp, [r11+48h]
0x180005e5c  mov     rsp, r11
0x180005e5f  pop     r15
0x180005e61  pop     r14
0x180005e63  pop     r12
0x180005e65  pop     rdi
0x180005e66  pop     rsi
0x180005e67  retn
```
