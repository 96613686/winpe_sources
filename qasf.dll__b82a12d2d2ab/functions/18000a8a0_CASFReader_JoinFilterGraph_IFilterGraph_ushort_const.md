# CASFReader::JoinFilterGraph(IFilterGraph *,ushort const *)

- ea: `0x18000a8a0`
- end: `0x18000aa48`
- name: `?JoinFilterGraph@CASFReader@@UEAAJPEAUIFilterGraph@@PEBG@Z`
- size: `424`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct IFilterGraph *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004f90`
- `0x180006ed0`
- `0x180009474`
- `0x18000a8a0`
- `0x18000ab04`
- `0x18001f010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000a901`
- `ole32!CoCreateInstance` at `0x18000a901`

## pseudocode

```c
__int64 __fastcall CASFReader::JoinFilterGraph(LPVOID *this, struct IFilterGraph *a2, const unsigned __int16 *a3)
{
  CASFReader *v3; // rsi
  _QWORD *v7; // rsi
  int Instance; // edi
  unsigned int v9; // eax
  unsigned __int64 v10; // rdx

  v3 = (CASFReader *)(this - 3);
  if ( !this[9] && a2 )
  {
    CASFReader::Detect6_4WMPGraph((CASFReader *)(this - 3), a2);
    if ( *((_DWORD *)this + 116) )
    {
      v7 = this + 55;
      Instance = CoCreateInstance(&CLSID_LegacyNetShowSource, 0, 3u, &IID_IBaseFilter, this + 55);
      if ( Instance >= 0 )
      {
        Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v7)(
                     *v7,
                     &IID_IFileSourceFilter,
                     (char *)this + 448);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_IUnknown, (char *)this + 456);
          if ( Instance >= 0 )
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, struct IFilterGraph *, const unsigned __int16 *))(*(_QWORD *)*v7 + 104LL))(
                                   *v7,
                                   a2,
                                   a3);
        }
      }
      return (unsigned int)Instance;
    }
    goto LABEL_16;
  }
  if ( !*((_DWORD *)this + 116) )
  {
LABEL_16:
    Instance = CBaseFilter::JoinFilterGraph((CBaseFilter *)this, a2, a3);
    if ( Instance >= 0 )
    {
      if ( this[9] )
      {
        if ( this[27] )
        {
          if ( !this[40] )
          {
            Instance = CASFReader::LoadInternal(v3, v10);
            if ( Instance < 0 )
              CBaseFilter::JoinFilterGraph((CBaseFilter *)this, 0, 0);
          }
        }
      }
    }
    return (unsigned int)Instance;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)this[55] + 104LL))(this[55]);
  if ( !a2 )
  {
    v9 = 0;
    if ( this[56] )
    {
      this[56] = 0;
      v9 = CUnknown::NonDelegatingRelease(v3);
    }
    if ( this[55] )
    {
      this[55] = 0;
      if ( v9 )
        CUnknown::NonDelegatingRelease(v3);
    }
    *((_DWORD *)this + 117) = 1;
    *((_DWORD *)this + 116) = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000a8a0  push    rbx
0x18000a8a2  push    rbp
0x18000a8a3  push    rsi
0x18000a8a4  push    rdi
0x18000a8a5  push    r14
0x18000a8a7  sub     rsp, 30h
0x18000a8ab  lea     rsi, [rcx-18h]
0x18000a8af  mov     r14, r8
0x18000a8b2  cmp     qword ptr [rsi+60h], 0
0x18000a8b7  mov     rbp, rdx
0x18000a8ba  mov     rbx, rcx
0x18000a8bd  jnz     loc_18000A979
0x18000a8c3  test    rdx, rdx
0x18000a8c6  jz      loc_18000A979
0x18000a8cc  mov     rcx, rsi; this
0x18000a8cf  call    ?Detect6_4WMPGraph@CASFReader@@AEAAXPEAUIFilterGraph@@@Z; CASFReader::Detect6_4WMPGraph(IFilterGraph *)
0x18000a8d4  cmp     dword ptr [rbx+1D0h], 0
0x18000a8db  jz      loc_18000A9F1
0x18000a8e1  xor     edx, edx; pUnkOuter
0x18000a8e3  lea     rsi, [rbx+1B8h]
0x18000a8ea  lea     r9, IID_IBaseFilter; riid
0x18000a8f1  mov     [rsp+58h+ppv], rsi; ppv
0x18000a8f6  lea     rcx, CLSID_LegacyNetShowSource; rclsid
0x18000a8fd  lea     r8d, [rdx+3]; dwClsContext
0x18000a901  call    cs:__imp_CoCreateInstance
0x18000a907  mov     edi, eax
0x18000a909  test    eax, eax
0x18000a90b  js      loc_18000AA3B
0x18000a911  mov     rcx, [rsi]
0x18000a914  lea     r8, [rbx+1C0h]
0x18000a91b  lea     rdx, IID_IFileSourceFilter
0x18000a922  mov     rax, [rcx]
0x18000a925  mov     rax, [rax]
0x18000a928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a92d  mov     edi, eax
0x18000a92f  test    eax, eax
0x18000a931  js      loc_18000AA3B
0x18000a937  mov     rcx, [rsi]
0x18000a93a  lea     r8, [rbx+1C8h]
0x18000a941  lea     rdx, IID_IUnknown
0x18000a948  mov     rax, [rcx]
0x18000a94b  mov     rax, [rax]
0x18000a94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a953  mov     edi, eax
0x18000a955  test    eax, eax
0x18000a957  js      loc_18000AA3B
0x18000a95d  mov     rcx, [rsi]
0x18000a960  mov     r8, r14
0x18000a963  mov     rdx, rbp
0x18000a966  mov     rax, [rcx]
0x18000a969  mov     rax, [rax+68h]
0x18000a96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a972  mov     edi, eax
0x18000a974  jmp     loc_18000AA3B
0x18000a979  cmp     dword ptr [rcx+1D0h], 0
0x18000a980  jz      short loc_18000A9F1
0x18000a982  mov     rcx, [rcx+1B8h]
0x18000a989  mov     rax, [rcx]
0x18000a98c  mov     rax, [rax+68h]
0x18000a990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a995  mov     edi, eax
0x18000a997  test    rbp, rbp
0x18000a99a  jnz     loc_18000AA3B
0x18000a9a0  xor     eax, eax
0x18000a9a2  cmp     [rbx+1C0h], rax
0x18000a9a9  jz      short loc_18000A9BA
0x18000a9ab  mov     rcx, rsi; this
0x18000a9ae  mov     [rbx+1C0h], rax
0x18000a9b5  call    ?NonDelegatingRelease@CUnknown@@UEAAKXZ; CUnknown::NonDelegatingRelease(void)
0x18000a9ba  cmp     qword ptr [rbx+1B8h], 0
0x18000a9c2  jz      short loc_18000A9DB
0x18000a9c4  mov     qword ptr [rbx+1B8h], 0
0x18000a9cf  test    eax, eax
0x18000a9d1  jz      short loc_18000A9DB
0x18000a9d3  mov     rcx, rsi; this
0x18000a9d6  call    ?NonDelegatingRelease@CUnknown@@UEAAKXZ; CUnknown::NonDelegatingRelease(void)
0x18000a9db  mov     dword ptr [rbx+1D4h], 1
0x18000a9e5  mov     dword ptr [rbx+1D0h], 0
0x18000a9ef  jmp     short loc_18000AA3B
0x18000a9f1  mov     r8, r14; unsigned __int16 *
0x18000a9f4  mov     rdx, rbp; struct IFilterGraph *
0x18000a9f7  mov     rcx, rbx; this
0x18000a9fa  call    ?JoinFilterGraph@CBaseFilter@@UEAAJPEAUIFilterGraph@@PEBG@Z; CBaseFilter::JoinFilterGraph(IFilterGraph *,ushort const *)
0x18000a9ff  mov     edi, eax
0x18000aa01  test    eax, eax
0x18000aa03  js      short loc_18000AA3B
0x18000aa05  cmp     qword ptr [rbx+48h], 0
0x18000aa0a  jz      short loc_18000AA3B
0x18000aa0c  cmp     qword ptr [rbx+0D8h], 0
0x18000aa14  jz      short loc_18000AA3B
0x18000aa16  cmp     qword ptr [rbx+140h], 0
0x18000aa1e  jnz     short loc_18000AA3B
0x18000aa20  mov     rcx, rsi; this
0x18000aa23  call    ?LoadInternal@CASFReader@@QEAAJXZ; CASFReader::LoadInternal(void)
0x18000aa28  mov     edi, eax
0x18000aa2a  test    eax, eax
0x18000aa2c  jns     short loc_18000AA3B
0x18000aa2e  xor     r8d, r8d; unsigned __int16 *
0x18000aa31  xor     edx, edx; struct IFilterGraph *
0x18000aa33  mov     rcx, rbx; this
0x18000aa36  call    ?JoinFilterGraph@CBaseFilter@@UEAAJPEAUIFilterGraph@@PEBG@Z; CBaseFilter::JoinFilterGraph(IFilterGraph *,ushort const *)
0x18000aa3b  mov     eax, edi
0x18000aa3d  add     rsp, 30h
0x18000aa41  pop     r14
0x18000aa43  pop     rdi
0x18000aa44  pop     rsi
0x18000aa45  pop     rbp
0x18000aa46  pop     rbx
0x18000aa47  retn
```
