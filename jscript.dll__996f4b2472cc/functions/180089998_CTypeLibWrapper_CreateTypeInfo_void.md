# CTypeLibWrapper::CreateTypeInfo(void)

- ea: `0x180089998`
- end: `0x180089bcc`
- name: `?CreateTypeInfo@CTypeLibWrapper@@AEAAJXZ`
- size: `564`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180089ca0`

## callees

- `0x18000c860`
- `0x18000c8c0`
- `0x180074ecc`
- `0x180089998`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180089a35`
- `msvcrt!_ultow_s` at `0x180089a35`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::CreateTypeInfo(CTypeLibWrapper *this)
{
  int DispatchTypeInfo; // ebx
  unsigned int v4; // esi
  unsigned int v5; // r12d
  __int64 v6; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v7; // [rsp+38h] [rbp-41h] BYREF
  struct ITypeInfo *v8; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v9[8]; // [rsp+50h] [rbp-29h] BYREF
  __int16 v10; // [rsp+70h] [rbp-9h]
  __int16 v11; // [rsp+88h] [rbp+Fh]
  int v12; // [rsp+8Ch] [rbp+13h]
  wchar_t Buffer[12]; // [rsp+90h] [rbp+17h] BYREF

  v8 = 0;
  v6 = 0;
  if ( !(unsigned int)MUTX::Enter((CTypeLibWrapper *)((char *)this + 48)) )
    return 2147500037LL;
  if ( *((_QWORD *)this + 5) )
  {
    DispatchTypeInfo = 0;
  }
  else
  {
    DispatchTypeInfo = GetDispatchTypeInfo(&v8);
    if ( DispatchTypeInfo >= 0 )
    {
      memset(Buffer, 0, 22);
      _ultow_s(_InterlockedIncrement(&dword_1800B8F80), Buffer, 0xBu, 10);
      DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, __int64, __int64 *))(**((_QWORD **)this + 4)
                                                                                          + 24LL))(
                           *((_QWORD *)this + 4),
                           Buffer,
                           4,
                           &v6);
      if ( DispatchTypeInfo >= 0 )
      {
        v7 = 0;
        DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, struct ITypeInfo *, unsigned int *))(*(_QWORD *)v6 + 64LL))(
                             v6,
                             v8,
                             &v7);
        if ( DispatchTypeInfo >= 0 )
        {
          DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 80LL))(v6, 0, v7);
          if ( DispatchTypeInfo >= 0 )
          {
            memset_0(v9, 0, 0x40u);
            v12 = 3;
            v10 = 12;
            v4 = 0;
            v11 = 0;
            if ( *((_DWORD *)this + 3) )
            {
              while ( 1 )
              {
                v5 = v4 + 1;
                v9[0] = v4 + 1;
                DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v6 + 112LL))(
                                     v6,
                                     v4,
                                     v9);
                if ( DispatchTypeInfo < 0 )
                  break;
                DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 128LL))(
                                     v6,
                                     v4,
                                     *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 16LL * v4 + 8));
                if ( DispatchTypeInfo < 0 )
                  break;
                ++v4;
                if ( v5 >= *((_DWORD *)this + 3) )
                  goto LABEL_13;
              }
            }
            else
            {
LABEL_13:
              DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 200LL))(v6);
              if ( DispatchTypeInfo >= 0 )
                DispatchTypeInfo = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v6)(
                                     v6,
                                     &IID_ITypeInfo,
                                     (char *)this + 40);
            }
          }
        }
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v8 )
    ((void (__fastcall *)(struct ITypeInfo *))v8->lpVtbl->Release)(v8);
  MUTX::Leave((CTypeLibWrapper *)((char *)this + 48));
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x180089998  mov     [rsp-8+arg_8], rbx
0x18008999d  mov     [rsp-8+arg_10], rsi
0x1800899a2  push    rbp
0x1800899a3  push    rdi
0x1800899a4  push    r12
0x1800899a6  push    r14
0x1800899a8  push    r15
0x1800899aa  lea     rbp, [rsp-37h]
0x1800899af  sub     rsp, 0B0h
0x1800899b6  mov     rax, cs:__security_cookie
0x1800899bd  xor     rax, rsp
0x1800899c0  mov     [rbp+57h+var_28], rax
0x1800899c4  mov     rdi, rcx
0x1800899c7  mov     [rbp+57h+var_90], 0
0x1800899cf  add     rcx, 30h ; '0'; this
0x1800899d3  mov     [rbp+57h+var_A0], 0
0x1800899db  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x1800899e0  test    eax, eax
0x1800899e2  jnz     short loc_1800899EE
0x1800899e4  mov     eax, 80004005h
0x1800899e9  jmp     loc_180089BA3
0x1800899ee  cmp     qword ptr [rdi+28h], 0
0x1800899f3  jz      short loc_1800899FC
0x1800899f5  xor     ebx, ebx
0x1800899f7  jmp     loc_180089B6E
0x1800899fc  lea     rcx, [rbp+57h+var_90]; struct ITypeInfo **
0x180089a00  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x180089a05  mov     ebx, eax
0x180089a07  test    eax, eax
0x180089a09  js      loc_180089B6E
0x180089a0f  xor     eax, eax
0x180089a11  xorps   xmm0, xmm0
0x180089a14  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180089a18  mov     qword ptr [rbp+57h+Buffer+0Eh], rax
0x180089a1c  lea     ecx, [rax+1]
0x180089a1f  lock xadd cs:dword_1800B8F80, ecx
0x180089a27  inc     ecx; Value
0x180089a29  lea     r9d, [rax+0Ah]; Radix
0x180089a2d  lea     r8d, [rax+0Bh]; BufferCount
0x180089a31  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180089a35  call    cs:__imp__ultow_s
0x180089a3c  nop     dword ptr [rax+rax+00h]
0x180089a41  mov     rcx, [rdi+20h]
0x180089a45  lea     r9, [rbp+57h+var_A0]
0x180089a49  mov     r8d, 4
0x180089a4f  lea     rdx, [rbp+57h+Buffer]
0x180089a53  mov     rax, [rcx]
0x180089a56  mov     rax, [rax+18h]
0x180089a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a5f  mov     ebx, eax
0x180089a61  test    eax, eax
0x180089a63  js      loc_180089B6E
0x180089a69  mov     rcx, [rbp+57h+var_A0]
0x180089a6d  lea     r8, [rbp+57h+var_98]
0x180089a71  mov     rdx, [rbp+57h+var_90]
0x180089a75  mov     [rbp+57h+var_98], 0
0x180089a7c  mov     rax, [rcx]
0x180089a7f  mov     rax, [rax+40h]
0x180089a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a88  mov     ebx, eax
0x180089a8a  test    eax, eax
0x180089a8c  js      loc_180089B6E
0x180089a92  mov     rcx, [rbp+57h+var_A0]
0x180089a96  xor     edx, edx
0x180089a98  mov     r8d, [rbp+57h+var_98]
0x180089a9c  mov     rax, [rcx]
0x180089a9f  mov     rax, [rax+50h]
0x180089aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089aa8  mov     ebx, eax
0x180089aaa  test    eax, eax
0x180089aac  js      loc_180089B6E
0x180089ab2  xor     edx, edx; Val
0x180089ab4  lea     rcx, [rbp+57h+var_80]; void *
0x180089ab8  lea     r8d, [rdx+40h]; Size
0x180089abc  call    memset_0
0x180089ac1  mov     eax, 0Ch
0x180089ac6  mov     [rbp+57h+var_44], 3
0x180089acd  mov     [rbp+57h+var_60], ax
0x180089ad1  xor     esi, esi
0x180089ad3  xor     eax, eax
0x180089ad5  mov     [rbp+57h+var_48], ax
0x180089ad9  cmp     [rdi+0Ch], eax
0x180089adc  jbe     short loc_180089B39
0x180089ade  mov     rcx, [rbp+57h+var_A0]
0x180089ae2  lea     r12d, [rsi+1]
0x180089ae6  mov     [rbp+57h+var_80], r12d
0x180089aea  lea     r8, [rbp+57h+var_80]
0x180089aee  mov     edx, esi
0x180089af0  mov     rax, [rcx]
0x180089af3  mov     rax, [rax+70h]
0x180089af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089afc  mov     ebx, eax
0x180089afe  test    eax, eax
0x180089b00  js      short loc_180089B6E
0x180089b02  mov     rax, [rdi+10h]
0x180089b06  mov     edx, esi
0x180089b08  mov     rcx, [rbp+57h+var_A0]
0x180089b0c  mov     r10d, esi
0x180089b0f  add     r10, r10
0x180089b12  mov     r8, [rax+18h]
0x180089b16  mov     r9, [rcx]
0x180089b19  mov     r8, [r8+r10*8+8]
0x180089b1e  mov     rax, [r9+80h]
0x180089b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b2a  mov     ebx, eax
0x180089b2c  test    eax, eax
0x180089b2e  js      short loc_180089B6E
0x180089b30  mov     esi, r12d
0x180089b33  cmp     r12d, [rdi+0Ch]
0x180089b37  jb      short loc_180089ADE
0x180089b39  mov     rcx, [rbp+57h+var_A0]
0x180089b3d  mov     rax, [rcx]
0x180089b40  mov     rax, [rax+0C8h]
0x180089b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b4c  mov     ebx, eax
0x180089b4e  test    eax, eax
0x180089b50  js      short loc_180089B6E
0x180089b52  mov     rcx, [rbp+57h+var_A0]
0x180089b56  lea     r8, [rdi+28h]
0x180089b5a  lea     rdx, IID_ITypeInfo
0x180089b61  mov     rax, [rcx]
0x180089b64  mov     rax, [rax]
0x180089b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b6c  mov     ebx, eax
0x180089b6e  mov     rcx, [rbp+57h+var_A0]
0x180089b72  test    rcx, rcx
0x180089b75  jz      short loc_180089B83
0x180089b77  mov     rax, [rcx]
0x180089b7a  mov     rax, [rax+10h]
0x180089b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b83  mov     rcx, [rbp+57h+var_90]
0x180089b87  test    rcx, rcx
0x180089b8a  jz      short loc_180089B98
0x180089b8c  mov     rax, [rcx]
0x180089b8f  mov     rax, [rax+10h]
0x180089b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b98  lea     rcx, [rdi+30h]; this
0x180089b9c  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180089ba1  mov     eax, ebx
0x180089ba3  mov     rcx, [rbp+57h+var_28]
0x180089ba7  xor     rcx, rsp; StackCookie
0x180089baa  call    __security_check_cookie
0x180089baf  lea     r11, [rsp+0D0h+var_20]
0x180089bb7  mov     rbx, [r11+38h]
0x180089bbb  mov     rsi, [r11+40h]
0x180089bbf  mov     rsp, r11
0x180089bc2  pop     r15
0x180089bc4  pop     r14
0x180089bc6  pop     r12
0x180089bc8  pop     rdi
0x180089bc9  pop     rbp
0x180089bca  retn
```
