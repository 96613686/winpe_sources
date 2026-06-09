# DdmDevice::AcceptNewLink(RasObjPtr<DdmConnection> &)

- ea: `0x180031cf0`
- end: `0x180031f47`
- name: `?AcceptNewLink@DdmDevice@@UEAAHAEAV?$RasObjPtr@VDdmConnection@@@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(DdmDevice *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007d00`
- `0x180031cf0`
- `0x180035e2c`
- `0x180035f14`
- `0x180075588`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180031e9b`
- `KERNEL32!LeaveCriticalSection` at `0x180031eed`
- `KERNEL32!LeaveCriticalSection` at `0x180031e9b`
- `KERNEL32!LeaveCriticalSection` at `0x180031eed`
- `KERNEL32!EnterCriticalSection` at `0x180031d73`
- `KERNEL32!EnterCriticalSection` at `0x180031d73`

## string_xrefs

- `0x180031e05`: `AcceptNewLink: Skipping version 1 Admin Dll callback for IKEv2 connection`

## pseudocode

```c
__int64 __fastcall DdmDevice::AcceptNewLink(DdmDevice *this, __int64 a2)
{
  unsigned int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v6; // r12d
  __int64 v7; // rsi
  int i; // r13d
  unsigned int (__fastcall **v9)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *); // r14
  __int64 v10; // rdx
  __int64 v12; // rdi
  void (__fastcall *v13)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *); // rax
  struct _RAS_PORT_1 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+80h] [rbp-80h] BYREF
  struct _RAS_PORT_0 v16; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+220h] [rbp+120h] BYREF
  __int128 v18; // [rsp+224h] [rbp+124h]
  __int128 v19; // [rsp+234h] [rbp+134h]
  int v20; // [rsp+244h] [rbp+144h]

  memset_0(&v16, 0, sizeof(v16));
  memset_0(&v14, 0, sizeof(v14));
  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a2 + 16LL);
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  v15 = 0;
  EnterCriticalSection(v5);
  v6 = 1;
  v7 = 0;
  for ( i = *(_DWORD *)(*(_QWORD *)a2 + 80LL) & 0x80; (unsigned int)v7 < dword_1800CF568; v7 = (unsigned int)(v7 + 1) )
  {
    v9 = (unsigned int (__fastcall **)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *))((char *)qword_1800CF560
                                                                                  + 168 * (unsigned int)v7);
    if ( i && *((_BYTE *)v9 + 8) == 1 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v17) = 0;
        if ( this )
          v10 = *((unsigned int *)this + 24);
        else
          v10 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v17, v10);
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)L"AcceptNewLink: Skipping version 1 Admin Dll callback for IKEv2 connection",
            (unsigned int)&v15,
            0,
            (__int64)&v17);
      }
    }
    else if ( v9[9] )
    {
      if ( v6 )
      {
        v6 = 0;
        if ( DdmDevice::GetRasPortData(this, &v16) || DdmDevice::GetRasPortData(this, &v14) )
        {
          (*(void (__fastcall **)(DdmDevice *))(*(_QWORD *)this + 176LL))(this);
          LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a2 + 16LL));
          return 0;
        }
        *((_DWORD *)this + 33) &= ~0x20u;
      }
      if ( !v9[9](&v16, &v14) )
      {
        (*(void (__fastcall **)(DdmDevice *))(*(_QWORD *)this + 176LL))(this);
        if ( (_DWORD)v7 )
        {
          v12 = 0;
          do
          {
            v13 = *(void (__fastcall **)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *))((char *)qword_1800CF560 + v12 + 104);
            if ( v13 )
              v13(&v16, &v14);
            v12 += 168;
            --v7;
          }
          while ( v7 );
        }
        goto LABEL_18;
      }
    }
  }
  *((_DWORD *)this + 33) |= 0x20u;
  v4 = 1;
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a2 + 16LL));
  return v4;
}

```

## disassembly

```asm
0x180031cf0  mov     [rsp-8+arg_10], rbx
0x180031cf5  push    rbp
0x180031cf6  push    rsi
0x180031cf7  push    rdi
0x180031cf8  push    r12
0x180031cfa  push    r13
0x180031cfc  push    r14
0x180031cfe  push    r15
0x180031d00  lea     rbp, [rsp-150h]
0x180031d08  sub     rsp, 250h
0x180031d0f  mov     rax, cs:__security_cookie
0x180031d16  xor     rax, rsp
0x180031d19  mov     [rbp+180h+var_38], rax
0x180031d20  mov     r15, rdx
0x180031d23  mov     rdi, rcx
0x180031d26  xor     edx, edx; Val
0x180031d28  lea     rcx, [rbp+180h+var_1F0]; void *
0x180031d2c  mov     r8d, 188h; Size
0x180031d32  call    memset_0
0x180031d37  xor     edx, edx; Val
0x180031d39  lea     rcx, [rsp+280h+var_250]; void *
0x180031d3e  lea     r8d, [rdx+48h]; Size
0x180031d42  call    memset_0
0x180031d47  mov     rcx, [r15]
0x180031d4a  xorps   xmm0, xmm0
0x180031d4d  xor     eax, eax
0x180031d4f  xor     ebx, ebx
0x180031d51  add     rcx, 10h; lpCriticalSection
0x180031d55  mov     [rbp+180h+var_60], ebx
0x180031d5b  movups  [rbp+180h+var_5C], xmm0
0x180031d62  mov     [rbp+180h+var_3C], eax
0x180031d68  movups  [rbp+180h+var_4C], xmm0
0x180031d6f  movups  [rbp+180h+var_200], xmm0
0x180031d73  call    cs:__imp_EnterCriticalSection
0x180031d7a  nop     dword ptr [rax+rax+00h]
0x180031d7f  mov     rax, [r15]
0x180031d82  lea     r12d, [rbx+1]
0x180031d86  mov     esi, ebx
0x180031d88  mov     r13d, [rax+50h]
0x180031d8c  and     r13d, 80h
0x180031d93  cmp     cs:dword_1800CF568, ebx
0x180031d99  jbe     loc_180031E88
0x180031d9f  mov     eax, esi
0x180031da1  imul    r14, rax, 0A8h
0x180031da8  add     r14, cs:qword_1800CF560
0x180031daf  test    r13d, r13d
0x180031db2  jz      short loc_180031E26
0x180031db4  cmp     byte ptr [r14+8], 1
0x180031db9  jnz     short loc_180031E26
0x180031dbb  test    cs:byte_1800CF404, 8
0x180031dc2  jz      loc_180031E7A
0x180031dc8  mov     word ptr [rbp+180h+var_60], bx
0x180031dcf  test    rdi, rdi
0x180031dd2  jz      short loc_180031DD9
0x180031dd4  mov     edx, [rdi+60h]
0x180031dd7  jmp     short loc_180031DDC
0x180031dd9  or      edx, 0FFFFFFFFh
0x180031ddc  lea     rcx, [rbp+180h+var_60]
0x180031de3  call    ConvertPortNoToString
0x180031de8  test    cs:byte_1800CF404, 8
0x180031def  jz      loc_180031E7A
0x180031df5  lea     rax, [rbp+180h+var_60]
0x180031dfc  mov     [rsp+280h+var_258], rax
0x180031e01  lea     r9, [rbp+180h+var_200]
0x180031e05  lea     r8, aAcceptnewlinkS; "AcceptNewLink: Skipping version 1 Admin"...
0x180031e0c  mov     [rsp+280h+var_260], rbx
0x180031e11  lea     rdx, RasDdmParamTraceError
0x180031e18  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031e1f  call    McTemplateU0zjzz_EventWriteTransfer
0x180031e24  jmp     short loc_180031E7A
0x180031e26  cmp     [r14+48h], rbx
0x180031e2a  jz      short loc_180031E7A
0x180031e2c  test    r12d, r12d
0x180031e2f  jz      short loc_180031E60
0x180031e31  lea     rdx, [rbp+180h+var_1F0]; struct _RAS_PORT_0 *
0x180031e35  mov     rcx, rdi; this
0x180031e38  mov     r12d, ebx
0x180031e3b  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_0@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_0 *)
0x180031e40  test    eax, eax
0x180031e42  jnz     loc_180031ED4
0x180031e48  lea     rdx, [rsp+280h+var_250]; struct _RAS_PORT_1 *
0x180031e4d  mov     rcx, rdi; this
0x180031e50  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_1@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_1 *)
0x180031e55  test    eax, eax
0x180031e57  jnz     short loc_180031ED4
0x180031e59  and     dword ptr [rdi+84h], 0FFFFFFDFh
0x180031e60  mov     rax, [r14+48h]
0x180031e64  lea     rdx, [rsp+280h+var_250]
0x180031e69  lea     rcx, [rbp+180h+var_1F0]
0x180031e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e72  test    eax, eax
0x180031e74  jz      loc_180031EFD
0x180031e7a  inc     esi
0x180031e7c  cmp     esi, cs:dword_1800CF568
0x180031e82  jb      loc_180031D9F
0x180031e88  or      dword ptr [rdi+84h], 20h
0x180031e8f  mov     ebx, 1
0x180031e94  mov     rcx, [r15]
0x180031e97  add     rcx, 10h; lpCriticalSection
0x180031e9b  call    cs:__imp_LeaveCriticalSection
0x180031ea2  nop     dword ptr [rax+rax+00h]
0x180031ea7  mov     eax, ebx
0x180031ea9  mov     rcx, [rbp+180h+var_38]
0x180031eb0  xor     rcx, rsp; StackCookie
0x180031eb3  call    __security_check_cookie
0x180031eb8  mov     rbx, [rsp+280h+arg_10]
0x180031ec0  add     rsp, 250h
0x180031ec7  pop     r15
0x180031ec9  pop     r14
0x180031ecb  pop     r13
0x180031ecd  pop     r12
0x180031ecf  pop     rdi
0x180031ed0  pop     rsi
0x180031ed1  pop     rbp
0x180031ed2  retn
0x180031ed4  mov     rax, [rdi]
0x180031ed7  mov     rcx, rdi
0x180031eda  mov     rax, [rax+0B0h]
0x180031ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ee6  mov     rcx, [r15]
0x180031ee9  add     rcx, 10h; lpCriticalSection
0x180031eed  call    cs:__imp_LeaveCriticalSection
0x180031ef4  nop     dword ptr [rax+rax+00h]
0x180031ef9  xor     eax, eax
0x180031efb  jmp     short loc_180031EA9
0x180031efd  mov     rax, [rdi]
0x180031f00  mov     rcx, rdi
0x180031f03  mov     rax, [rax+0B0h]
0x180031f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f0f  test    esi, esi
0x180031f11  jz      short loc_180031E94
0x180031f13  mov     rdi, rbx
0x180031f16  mov     rax, cs:qword_1800CF560
0x180031f1d  mov     rax, [rdi+rax+68h]
0x180031f22  test    rax, rax
0x180031f25  jz      short loc_180031F35
0x180031f27  lea     rdx, [rsp+280h+var_250]
0x180031f2c  lea     rcx, [rbp+180h+var_1F0]
0x180031f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f35  add     rdi, 0A8h
0x180031f3c  sub     rsi, 1
0x180031f40  jnz     short loc_180031F16
0x180031f42  jmp     loc_180031E94
```
