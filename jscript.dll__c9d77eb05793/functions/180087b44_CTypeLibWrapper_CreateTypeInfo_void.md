# CTypeLibWrapper::CreateTypeInfo(void)

- ea: `0x180087b44`
- end: `0x180087d71`
- name: `?CreateTypeInfo@CTypeLibWrapper@@AEAAJXZ`
- size: `557`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180087e40`

## callees

- `0x18000f5e0`
- `0x18000f630`
- `0x180073a08`
- `0x180087b44`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180087be1`
- `msvcrt!_ultow_s` at `0x180087be1`

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
      _ultow_s(_InterlockedIncrement(&dword_1800B6F80), Buffer, 0xBu, 10);
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
0x180087b44  mov     [rsp-8+arg_8], rbx
0x180087b49  mov     [rsp-8+arg_10], rsi
0x180087b4e  push    rbp
0x180087b4f  push    rdi
0x180087b50  push    r12
0x180087b52  push    r14
0x180087b54  push    r15
0x180087b56  lea     rbp, [rsp-37h]
0x180087b5b  sub     rsp, 0B0h
0x180087b62  mov     rax, cs:__security_cookie
0x180087b69  xor     rax, rsp
0x180087b6c  mov     [rbp+57h+var_28], rax
0x180087b70  mov     rdi, rcx
0x180087b73  mov     [rbp+57h+var_90], 0
0x180087b7b  add     rcx, 30h ; '0'; this
0x180087b7f  mov     [rbp+57h+var_A0], 0
0x180087b87  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180087b8c  test    eax, eax
0x180087b8e  jnz     short loc_180087B9A
0x180087b90  mov     eax, 80004005h
0x180087b95  jmp     loc_180087D49
0x180087b9a  cmp     qword ptr [rdi+28h], 0
0x180087b9f  jz      short loc_180087BA8
0x180087ba1  xor     ebx, ebx
0x180087ba3  jmp     loc_180087D14
0x180087ba8  lea     rcx, [rbp+57h+var_90]; struct ITypeInfo **
0x180087bac  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x180087bb1  mov     ebx, eax
0x180087bb3  test    eax, eax
0x180087bb5  js      loc_180087D14
0x180087bbb  xor     eax, eax
0x180087bbd  xorps   xmm0, xmm0
0x180087bc0  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180087bc4  mov     qword ptr [rbp+57h+Buffer+0Eh], rax
0x180087bc8  lea     ecx, [rax+1]
0x180087bcb  lock xadd cs:dword_1800B6F80, ecx
0x180087bd3  inc     ecx; Value
0x180087bd5  lea     r9d, [rax+0Ah]; Radix
0x180087bd9  lea     r8d, [rax+0Bh]; BufferCount
0x180087bdd  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180087be1  call    cs:__imp__ultow_s
0x180087be7  mov     rcx, [rdi+20h]
0x180087beb  lea     r9, [rbp+57h+var_A0]
0x180087bef  mov     r8d, 4
0x180087bf5  lea     rdx, [rbp+57h+Buffer]
0x180087bf9  mov     rax, [rcx]
0x180087bfc  mov     rax, [rax+18h]
0x180087c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087c05  mov     ebx, eax
0x180087c07  test    eax, eax
0x180087c09  js      loc_180087D14
0x180087c0f  mov     rcx, [rbp+57h+var_A0]
0x180087c13  lea     r8, [rbp+57h+var_98]
0x180087c17  mov     rdx, [rbp+57h+var_90]
0x180087c1b  mov     [rbp+57h+var_98], 0
0x180087c22  mov     rax, [rcx]
0x180087c25  mov     rax, [rax+40h]
0x180087c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087c2e  mov     ebx, eax
0x180087c30  test    eax, eax
0x180087c32  js      loc_180087D14
0x180087c38  mov     rcx, [rbp+57h+var_A0]
0x180087c3c  xor     edx, edx
0x180087c3e  mov     r8d, [rbp+57h+var_98]
0x180087c42  mov     rax, [rcx]
0x180087c45  mov     rax, [rax+50h]
0x180087c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087c4e  mov     ebx, eax
0x180087c50  test    eax, eax
0x180087c52  js      loc_180087D14
0x180087c58  xor     edx, edx; Val
0x180087c5a  lea     rcx, [rbp+57h+var_80]; void *
0x180087c5e  lea     r8d, [rdx+40h]; Size
0x180087c62  call    memset_0
0x180087c67  mov     eax, 0Ch
0x180087c6c  mov     [rbp+57h+var_44], 3
0x180087c73  mov     [rbp+57h+var_60], ax
0x180087c77  xor     esi, esi
0x180087c79  xor     eax, eax
0x180087c7b  mov     [rbp+57h+var_48], ax
0x180087c7f  cmp     [rdi+0Ch], eax
0x180087c82  jbe     short loc_180087CDF
0x180087c84  mov     rcx, [rbp+57h+var_A0]
0x180087c88  lea     r12d, [rsi+1]
0x180087c8c  mov     [rbp+57h+var_80], r12d
0x180087c90  lea     r8, [rbp+57h+var_80]
0x180087c94  mov     edx, esi
0x180087c96  mov     rax, [rcx]
0x180087c99  mov     rax, [rax+70h]
0x180087c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ca2  mov     ebx, eax
0x180087ca4  test    eax, eax
0x180087ca6  js      short loc_180087D14
0x180087ca8  mov     rax, [rdi+10h]
0x180087cac  mov     edx, esi
0x180087cae  mov     rcx, [rbp+57h+var_A0]
0x180087cb2  mov     r10d, esi
0x180087cb5  add     r10, r10
0x180087cb8  mov     r8, [rax+18h]
0x180087cbc  mov     r9, [rcx]
0x180087cbf  mov     r8, [r8+r10*8+8]
0x180087cc4  mov     rax, [r9+80h]
0x180087ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087cd0  mov     ebx, eax
0x180087cd2  test    eax, eax
0x180087cd4  js      short loc_180087D14
0x180087cd6  mov     esi, r12d
0x180087cd9  cmp     r12d, [rdi+0Ch]
0x180087cdd  jb      short loc_180087C84
0x180087cdf  mov     rcx, [rbp+57h+var_A0]
0x180087ce3  mov     rax, [rcx]
0x180087ce6  mov     rax, [rax+0C8h]
0x180087ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087cf2  mov     ebx, eax
0x180087cf4  test    eax, eax
0x180087cf6  js      short loc_180087D14
0x180087cf8  mov     rcx, [rbp+57h+var_A0]
0x180087cfc  lea     r8, [rdi+28h]
0x180087d00  lea     rdx, IID_ITypeInfo
0x180087d07  mov     rax, [rcx]
0x180087d0a  mov     rax, [rax]
0x180087d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d12  mov     ebx, eax
0x180087d14  mov     rcx, [rbp+57h+var_A0]
0x180087d18  test    rcx, rcx
0x180087d1b  jz      short loc_180087D29
0x180087d1d  mov     rax, [rcx]
0x180087d20  mov     rax, [rax+10h]
0x180087d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d29  mov     rcx, [rbp+57h+var_90]
0x180087d2d  test    rcx, rcx
0x180087d30  jz      short loc_180087D3E
0x180087d32  mov     rax, [rcx]
0x180087d35  mov     rax, [rax+10h]
0x180087d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d3e  lea     rcx, [rdi+30h]; this
0x180087d42  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180087d47  mov     eax, ebx
0x180087d49  mov     rcx, [rbp+57h+var_28]
0x180087d4d  xor     rcx, rsp; StackCookie
0x180087d50  call    __security_check_cookie
0x180087d55  lea     r11, [rsp+0D0h+var_20]
0x180087d5d  mov     rbx, [r11+38h]
0x180087d61  mov     rsi, [r11+40h]
0x180087d65  mov     rsp, r11
0x180087d68  pop     r15
0x180087d6a  pop     r14
0x180087d6c  pop     r12
0x180087d6e  pop     rdi
0x180087d6f  pop     rbp
0x180087d70  retn
```
