# CMSVidWebDVD::put_Bookmark(uchar *,ulong)

- ea: `0x1800b48a0`
- end: `0x1800b499a`
- name: `?put_Bookmark@CMSVidWebDVD@@UEAAJPEAEK@Z`
- size: `250`
- prototype: `__int64 __fastcall(CMSVidWebDVD *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006b38`
- `0x1800acfe4`
- `0x1800b42fc`
- `0x1800b48a0`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800b48d9`
- `ole32!CoCreateInstance` at `0x1800b48d9`
- `KERNEL32!Sleep` at `0x1800b496e`
- `KERNEL32!Sleep` at `0x1800b496e`

## pseudocode

```c
__int64 __fastcall CMSVidWebDVD::put_Bookmark(CMSVidWebDVD *this, unsigned __int8 *a2, unsigned int a3)
{
  HRESULT Instance; // eax
  CMSVidWebDVD *v7; // rcx
  HRESULT v8; // ebx
  int v9; // ebx
  CMSVidWebDVD *v10; // rcx
  int v11; // edx
  int v12; // eax
  int v13; // edi
  LPVOID ppv[7]; // [rsp+30h] [rbp-38h] BYREF
  CMSVidWebDVD *v16; // [rsp+88h] [rbp+20h] BYREF

  ppv[0] = 0;
  Instance = CoCreateInstance(&CLSID_DVDState, 0, 1u, &IID_IDvdState, ppv);
  v8 = Instance;
  if ( Instance >= 0 )
  {
    ATL::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>(
      &v16,
      ppv[0]);
    v10 = v16;
    if ( v16 )
    {
      v12 = (*(__int64 (__fastcall **)(CMSVidWebDVD *, unsigned __int8 *, _QWORD))(*(_QWORD *)v16 + 40LL))(v16, a2, a3);
      if ( v12 >= 0 )
      {
        v9 = -2147467259;
        v13 = 0;
        do
        {
          if ( v13 >= 50 )
            break;
          v9 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, __int64))(**((_QWORD **)this + 22) + 296LL))(
                 *((_QWORD *)this + 22),
                 ppv[0],
                 5);
          ++v13;
          Sleep(1u);
        }
        while ( v9 < 0 );
        goto LABEL_11;
      }
      v11 = v12;
    }
    else
    {
      v11 = v8;
    }
    v9 = CMSVidWebDVD::HandleError(v10, v11);
LABEL_11:
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v16);
    goto LABEL_12;
  }
  v9 = CMSVidWebDVD::HandleError(v7, Instance);
LABEL_12:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800b48a0  push    rbx
0x1800b48a2  push    rbp
0x1800b48a3  push    rsi
0x1800b48a4  push    rdi
0x1800b48a5  sub     rsp, 48h
0x1800b48a9  mov     rsi, rdx
0x1800b48ac  mov     [rsp+68h+var_38], 0
0x1800b48b5  xor     edx, edx; pUnkOuter
0x1800b48b7  lea     rax, [rsp+68h+var_38]
0x1800b48bc  mov     edi, r8d
0x1800b48bf  mov     [rsp+68h+ppv], rax; ppv
0x1800b48c4  mov     rbp, rcx
0x1800b48c7  lea     r9, IID_IDvdState; riid
0x1800b48ce  lea     rcx, CLSID_DVDState; rclsid
0x1800b48d5  lea     r8d, [rdx+1]; dwClsContext
0x1800b48d9  call    cs:__imp_CoCreateInstance
0x1800b48df  mov     ebx, eax
0x1800b48e1  test    eax, eax
0x1800b48e3  jns     short loc_1800B48F3
0x1800b48e5  mov     edx, eax; int
0x1800b48e7  call    ?HandleError@CMSVidWebDVD@@AEAAJJ@Z; CMSVidWebDVD::HandleError(long)
0x1800b48ec  mov     ebx, eax
0x1800b48ee  jmp     loc_1800B4985
0x1800b48f3  mov     rdx, [rsp+68h+var_38]
0x1800b48f8  lea     rcx, [rsp+68h+arg_18]
0x1800b4900  call    ??0?$CComQIPtr@UIPersistMemory@@$1?_GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>(IUnknown *)
0x1800b4905  mov     rcx, [rsp+68h+arg_18]; this
0x1800b490d  test    rcx, rcx
0x1800b4910  jnz     short loc_1800B491D
0x1800b4912  mov     edx, ebx; int
0x1800b4914  call    ?HandleError@CMSVidWebDVD@@AEAAJJ@Z; CMSVidWebDVD::HandleError(long)
0x1800b4919  mov     ebx, eax
0x1800b491b  jmp     short loc_1800B4978
0x1800b491d  mov     rax, [rcx]
0x1800b4920  mov     r8d, edi
0x1800b4923  mov     rdx, rsi
0x1800b4926  mov     rax, [rax+28h]
0x1800b492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b492f  test    eax, eax
0x1800b4931  jns     short loc_1800B4937
0x1800b4933  mov     edx, eax
0x1800b4935  jmp     short loc_1800B4914
0x1800b4937  mov     ebx, 80004005h
0x1800b493c  xor     edi, edi
0x1800b493e  cmp     edi, 32h ; '2'
0x1800b4941  jge     short loc_1800B4978
0x1800b4943  mov     rcx, [rbp+0B0h]
0x1800b494a  xor     r9d, r9d
0x1800b494d  mov     rdx, [rsp+68h+var_38]
0x1800b4952  mov     rax, [rcx]
0x1800b4955  lea     r8d, [r9+5]
0x1800b4959  mov     rax, [rax+128h]
0x1800b4960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4965  mov     ecx, 1; dwMilliseconds
0x1800b496a  mov     ebx, eax
0x1800b496c  inc     edi
0x1800b496e  call    cs:__imp_Sleep
0x1800b4974  test    ebx, ebx
0x1800b4976  js      short loc_1800B493E
0x1800b4978  lea     rcx, [rsp+68h+arg_18]
0x1800b4980  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b4985  lea     rcx, [rsp+68h+var_38]
0x1800b498a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b498f  mov     eax, ebx
0x1800b4991  add     rsp, 48h
0x1800b4995  pop     rdi
0x1800b4996  pop     rsi
0x1800b4997  pop     rbp
0x1800b4998  pop     rbx
0x1800b4999  retn
```
