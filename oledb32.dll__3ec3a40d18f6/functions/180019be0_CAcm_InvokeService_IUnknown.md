# CAcm::InvokeService(IUnknown *)

- ea: `0x180019be0`
- end: `0x180019f15`
- name: `?InvokeService@CAcm@@UEAAJPEAUIUnknown@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(CAcm *__hidden this, struct IUnknown *)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006ecc0`
- `0x180073de0`
- `0x1800764e0`
- `0x180078370`

## callees

- `0x180013870`
- `0x180019be0`
- `0x180026940`
- `0x180029560`
- `0x18002ec0c`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180019c04`
- `KERNEL32!EnterCriticalSection` at `0x180019c04`
- `KERNEL32!LeaveCriticalSection` at `0x180019ef7`
- `KERNEL32!LeaveCriticalSection` at `0x180019ef7`

## string_xrefs

- `0x180019c2b`: `<CAcm::InvokeService|OLEDB|ERR> `
- `0x180019ccb`: `<CAcm::InvokeService|OLEDB|ERR> `
- `0x180019ce9`: `<CAcm::InvokeService|OLEDB|ERR> `
- `0x180019dad`: `<CAcm::InvokeService|OLEDB|ERR> `
- `0x180019e22`: `<CAcm::InvokeService|OLEDB|ERR> `
- `0x180019e40`: `<CAcm::InvokeService|OLEDB|ERR> `
- `0x180019c46`: `<CAcm::InvokeService|Trace|HR> `
- `0x180019d04`: `<CAcm::InvokeService|Trace|HR> `
- `0x180019dc8`: `<CAcm::InvokeService|Trace|HR> `
- `0x180019e5b`: `<CAcm::InvokeService|Trace|HR> `
- `0x180019ed4`: `<CAcm::InvokeService|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAcm::InvokeService(CAcm *this, struct IUnknown *a2)
{
  int v4; // edi
  int v5; // edi
  __int64 v6; // r15
  unsigned __int64 i; // r14
  int v8; // edi
  int v10; // ebx
  int pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  int v12; // [rsp+24h] [rbp-44h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF
  int v14; // [rsp+2Ch] [rbp-3Ch] BYREF
  unsigned int v15; // [rsp+30h] [rbp-38h] BYREF
  CAcm *v16; // [rsp+38h] [rbp-30h]
  char v17; // [rsp+40h] [rbp-28h]
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  __int64 v19; // [rsp+78h] [rbp+10h] BYREF

  v4 = 0;
  v16 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  try
  {
    v17 = 1;
    if ( !a2 )
    {
      v5 = -2147024809;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024809, L"<CAcm::InvokeService|OLEDB|ERR> ", 0x132u);
        if ( (bidGblFlags & 2) != 0 )
          v5 = bidTraceHR(off_1800C8498[0], 313353, L"<CAcm::InvokeService|Trace|HR> ", 2147942487LL);
      }
      pExceptionObject = v5;
      throw (long *)&pExceptionObject;
    }
    if ( *((_QWORD *)this + 20) )
    {
      v18 = 0;
      ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(a2, &IID_IService, &v18);
      if ( !v18 )
      {
        v8 = -2147467262;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147467262, L"<CAcm::InvokeService|OLEDB|ERR> ", 0x14Cu);
          if ( (bidGblFlags & 2) != 0 )
            v8 = bidTraceHR(off_1800C8498[0], 339977, L"<CAcm::InvokeService|Trace|HR> ", 2147500034LL);
        }
        v13 = v8;
        throw (long *)&v13;
      }
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 24LL))(v18, *((_QWORD *)this + 20));
      if ( v4 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v4, L"<CAcm::InvokeService|OLEDB|ERR> ", 0x14Fu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v4, L"<CAcm::InvokeService|OLEDB|ERR> ", 0x14Fu);
            if ( (bidGblFlags & 2) != 0 )
              v4 = bidTraceHR(off_1800C8498[0], 343049, L"<CAcm::InvokeService|Trace|HR> ", (unsigned int)v4);
          }
        }
        v14 = v4;
        throw (long *)&v14;
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 16LL))(*((_QWORD *)this + 20));
      *((_QWORD *)this + 20) = a2;
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v18);
    }
    else
    {
      v6 = *((_QWORD *)this + 12);
      for ( i = 0; i < *((_QWORD *)this + 9); ++i )
      {
        v19 = 0;
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))a2->lpVtbl->QueryInterface)(a2, v6, &v19);
        if ( v4 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v4, L"<CAcm::InvokeService|OLEDB|ERR> ", 0x13Du);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v4, L"<CAcm::InvokeService|OLEDB|ERR> ", 0x13Du);
              if ( (bidGblFlags & 2) != 0 )
                v4 = bidTraceHR(off_1800C8498[0], 324617, L"<CAcm::InvokeService|Trace|HR> ", (unsigned int)v4);
            }
          }
          v12 = v4;
          throw (long *)&v12;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v6 += 16;
      }
      *((_QWORD *)this + 20) = a2;
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    }
  }
  catch ( long v15 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8BB8[0] )
    {
      v10 = v15;
      bidTraceA(off_1800C8498[0], 353280, off_1800C8BB8[0], v15);
    }
    else
    {
      v10 = v15;
    }
    LODWORD(v18) = v10;
    v4 = v10;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8BB0[0] )
      bidTraceA(off_1800C8498[0], 358400, off_1800C8BB0[0], 0);
    LODWORD(v18) = -2147418113;
    v4 = -2147418113;
  }
  if ( (bidGblFlags & 2) != 0 )
    v4 = bidTraceHR(off_1800C8498[0], 362505, L"<CAcm::InvokeService|Trace|HR> ", (unsigned int)v4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v16 + 24));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019be0  mov     [rsp+arg_10], rbx
0x180019be5  mov     [rsp+arg_18], rsi
0x180019bea  push    rdi
0x180019beb  push    r14
0x180019bed  push    r15
0x180019bef  sub     rsp, 50h
0x180019bf3  mov     rbx, rdx
0x180019bf6  mov     rsi, rcx
0x180019bf9  xor     edi, edi
0x180019bfb  mov     [rsp+68h+var_30], rcx
0x180019c00  add     rcx, 18h; lpCriticalSection
0x180019c04  call    cs:__imp_EnterCriticalSection
0x180019c0a  mov     [rsp+68h+var_28], 1
0x180019c0f  test    rbx, rbx
0x180019c12  jnz     short loc_180019C75
0x180019c14  mov     eax, cs:_bidGblFlags
0x180019c1a  mov     bl, 2
0x180019c1c  mov     edi, 80070057h
0x180019c21  test    bl, al
0x180019c23  jz      short loc_180019C60
0x180019c25  mov     r8d, 132h; unsigned int
0x180019c2b  lea     rdx, aCacmInvokeserv_0; "<CAcm::InvokeService|OLEDB|ERR> "
0x180019c32  mov     ecx, edi; int
0x180019c34  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180019c39  mov     eax, cs:_bidGblFlags
0x180019c3f  test    bl, al
0x180019c41  jz      short loc_180019C60
0x180019c43  mov     r9d, edi
0x180019c46  lea     r8, aCacmInvokeserv_1; "<CAcm::InvokeService|Trace|HR> "
0x180019c4d  mov     edx, 4C809h
0x180019c52  mov     rcx, cs:off_1800C8498; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180019c59  call    _bidTraceHR
0x180019c5e  mov     edi, eax
0x180019c60  mov     [rsp+68h+pExceptionObject], edi
0x180019c64  lea     rdx, _TI1J; pThrowInfo
0x180019c6b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180019c70  call    _CxxThrowException_0
0x180019c75  cmp     qword ptr [rsi+0A0h], 0
0x180019c7d  jnz     loc_180019D68
0x180019c83  mov     r15, [rsi+60h]
0x180019c87  xor     r14d, r14d
0x180019c8a  mov     rcx, rbx
0x180019c8d  cmp     r14, [rsi+48h]
0x180019c91  jnb     loc_180019D50
0x180019c97  mov     [rsp+68h+arg_8], 0
0x180019ca0  mov     rax, [rbx]
0x180019ca3  lea     r8, [rsp+68h+arg_8]
0x180019ca8  mov     rdx, r15
0x180019cab  mov     rax, [rax]
0x180019cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cb3  mov     edi, eax
0x180019cb5  test    eax, eax
0x180019cb7  jns     short loc_180019D33
0x180019cb9  mov     eax, cs:_bidGblFlags
0x180019cbf  mov     bl, 2
0x180019cc1  test    bl, al
0x180019cc3  jz      short loc_180019D1E
0x180019cc5  mov     r8d, 13Dh; unsigned int
0x180019ccb  lea     rdx, aCacmInvokeserv_0; "<CAcm::InvokeService|OLEDB|ERR> "
0x180019cd2  mov     ecx, edi; int
0x180019cd4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180019cd9  mov     eax, cs:_bidGblFlags
0x180019cdf  test    bl, al
0x180019ce1  jz      short loc_180019D1E
0x180019ce3  mov     r8d, 13Dh; unsigned int
0x180019ce9  lea     rdx, aCacmInvokeserv_0; "<CAcm::InvokeService|OLEDB|ERR> "
0x180019cf0  mov     ecx, edi; int
0x180019cf2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180019cf7  mov     eax, cs:_bidGblFlags
0x180019cfd  test    bl, al
0x180019cff  jz      short loc_180019D1E
0x180019d01  mov     r9d, edi
0x180019d04  lea     r8, aCacmInvokeserv_1; "<CAcm::InvokeService|Trace|HR> "
0x180019d0b  mov     edx, 4F409h
0x180019d10  mov     rcx, cs:off_1800C8498; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180019d17  call    _bidTraceHR
0x180019d1c  mov     edi, eax
0x180019d1e  mov     [rsp+68h+var_44], edi
0x180019d22  lea     rdx, _TI1J; pThrowInfo
0x180019d29  lea     rcx, [rsp+68h+var_44]; pExceptionObject
0x180019d2e  call    _CxxThrowException_0
0x180019d33  mov     rcx, [rsp+68h+arg_8]
0x180019d38  mov     rax, [rcx]
0x180019d3b  mov     rax, [rax+10h]
0x180019d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d44  inc     r14
0x180019d47  add     r15, 10h
0x180019d4b  jmp     loc_180019C8A
0x180019d50  mov     [rsi+0A0h], rbx
0x180019d57  mov     rax, [rbx]
0x180019d5a  mov     rax, [rax+8]
0x180019d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d63  jmp     loc_180019EBF
0x180019d68  mov     [rsp+68h+arg_0], 0
0x180019d71  mov     rax, [rbx]
0x180019d74  lea     r8, [rsp+68h+arg_0]
0x180019d79  lea     rdx, IID_IService
0x180019d80  mov     rcx, rbx
0x180019d83  mov     rax, [rax]
0x180019d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d8b  nop
0x180019d8c  mov     rcx, [rsp+68h+arg_0]
0x180019d91  test    rcx, rcx
0x180019d94  jnz     short loc_180019DF7
0x180019d96  mov     eax, cs:_bidGblFlags
0x180019d9c  mov     bl, 2
0x180019d9e  mov     edi, 80004002h
0x180019da3  test    bl, al
0x180019da5  jz      short loc_180019DE2
0x180019da7  mov     r8d, 14Ch; unsigned int
0x180019dad  lea     rdx, aCacmInvokeserv_0; "<CAcm::InvokeService|OLEDB|ERR> "
0x180019db4  mov     ecx, edi; int
0x180019db6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180019dbb  mov     eax, cs:_bidGblFlags
0x180019dc1  test    bl, al
0x180019dc3  jz      short loc_180019DE2
0x180019dc5  mov     r9d, edi
0x180019dc8  lea     r8, aCacmInvokeserv_1; "<CAcm::InvokeService|Trace|HR> "
0x180019dcf  mov     edx, 53009h
0x180019dd4  mov     rcx, cs:off_1800C8498; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180019ddb  call    _bidTraceHR
0x180019de0  mov     edi, eax
0x180019de2  mov     [rsp+68h+var_40], edi
0x180019de6  lea     rdx, _TI1J; pThrowInfo
0x180019ded  lea     rcx, [rsp+68h+var_40]; pExceptionObject
0x180019df2  call    _CxxThrowException_0
0x180019df7  mov     rax, [rcx]
0x180019dfa  mov     rdx, [rsi+0A0h]
0x180019e01  mov     rax, [rax+18h]
0x180019e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e0a  mov     edi, eax
0x180019e0c  test    eax, eax
0x180019e0e  jns     short loc_180019E8A
0x180019e10  mov     eax, cs:_bidGblFlags
0x180019e16  mov     bl, 2
0x180019e18  test    bl, al
0x180019e1a  jz      short loc_180019E75
0x180019e1c  mov     r8d, 14Fh; unsigned int
0x180019e22  lea     rdx, aCacmInvokeserv_0; "<CAcm::InvokeService|OLEDB|ERR> "
0x180019e29  mov     ecx, edi; int
0x180019e2b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180019e30  mov     eax, cs:_bidGblFlags
0x180019e36  test    bl, al
0x180019e38  jz      short loc_180019E75
0x180019e3a  mov     r8d, 14Fh; unsigned int
0x180019e40  lea     rdx, aCacmInvokeserv_0; "<CAcm::InvokeService|OLEDB|ERR> "
0x180019e47  mov     ecx, edi; int
0x180019e49  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180019e4e  mov     eax, cs:_bidGblFlags
0x180019e54  test    bl, al
0x180019e56  jz      short loc_180019E75
0x180019e58  mov     r9d, edi
0x180019e5b  lea     r8, aCacmInvokeserv_1; "<CAcm::InvokeService|Trace|HR> "
0x180019e62  mov     edx, 53C09h
0x180019e67  mov     rcx, cs:off_1800C8498; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180019e6e  call    _bidTraceHR
0x180019e73  mov     edi, eax
0x180019e75  mov     [rsp+68h+var_3C], edi
0x180019e79  lea     rdx, _TI1J; pThrowInfo
0x180019e80  lea     rcx, [rsp+68h+var_3C]; pExceptionObject
0x180019e85  call    _CxxThrowException_0
0x180019e8a  mov     rcx, [rsi+0A0h]
0x180019e91  mov     rax, [rcx]
0x180019e94  mov     rax, [rax+10h]
0x180019e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e9d  mov     [rsi+0A0h], rbx
0x180019ea4  mov     rax, [rbx]
0x180019ea7  mov     rcx, rbx
0x180019eaa  mov     rax, [rax+8]
0x180019eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eb3  nop
0x180019eb4  lea     rcx, [rsp+68h+arg_0]
0x180019eb9  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x180019ebe  nop
0x180019ebf  jmp     short loc_180019EC7
0x180019ec1  jmp     short $+2
0x180019ec3  mov     edi, dword ptr [rsp+68h+arg_0]
0x180019ec7  mov     bl, 2
0x180019ec9  test    byte ptr cs:_bidGblFlags, bl
0x180019ecf  jz      short loc_180019EEE
0x180019ed1  mov     r9d, edi
0x180019ed4  lea     r8, aCacmInvokeserv_1; "<CAcm::InvokeService|Trace|HR> "
0x180019edb  mov     edx, 58809h
0x180019ee0  mov     rcx, cs:off_1800C8498; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180019ee7  call    _bidTraceHR
0x180019eec  mov     edi, eax
0x180019eee  mov     rcx, [rsp+68h+var_30]
0x180019ef3  add     rcx, 18h; lpCriticalSection
0x180019ef7  call    cs:__imp_LeaveCriticalSection
0x180019efd  mov     eax, edi
0x180019eff  lea     r11, [rsp+68h+var_18]
0x180019f04  mov     rbx, [r11+30h]
0x180019f08  mov     rsi, [r11+38h]
0x180019f0c  mov     rsp, r11
0x180019f0f  pop     r15
0x180019f11  pop     r14
0x180019f13  pop     rdi
0x180019f14  retn
```
