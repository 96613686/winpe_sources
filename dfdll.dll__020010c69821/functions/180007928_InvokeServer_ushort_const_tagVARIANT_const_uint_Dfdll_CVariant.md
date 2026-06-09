# InvokeServer(ushort const *,tagVARIANT const *,uint,Dfdll::CVariant &)

- ea: `0x180007928`
- end: `0x180007a7a`
- name: `?InvokeServer@@YAJPEBGPEBUtagVARIANT@@IAEAVCVariant@Dfdll@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct tagVARIANT *, int, struct Dfdll::CVariant *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180002720`
- `0x180005010`
- `0x180005130`
- `0x180005400`
- `0x1800060d0`
- `0x1800074c0`
- `0x180007640`

## callees

- `0x180007928`
- `0x180008938`
- `0x18001efd0`

## import_xrefs

- `ole32!CoUninitialize` at `0x180007a55`
- `ole32!CoUninitialize` at `0x180007a55`
- `ole32!CoInitialize` at `0x180007962`
- `ole32!CoInitialize` at `0x180007962`

## pseudocode

```c
__int64 __fastcall InvokeServer(
        const unsigned __int16 *a1,
        const struct tagVARIANT *a2,
        int a3,
        struct Dfdll::CVariant *a4)
{
  HRESULT v7; // ebx
  int v8; // edi
  int v10; // [rsp+28h] [rbp-79h]
  unsigned int v11; // [rsp+58h] [rbp-49h] BYREF
  void **v12; // [rsp+60h] [rbp-41h]
  void *v13; // [rsp+68h] [rbp-39h] BYREF
  HRESULT v14; // [rsp+70h] [rbp-31h]
  _BYTE v15[4]; // [rsp+74h] [rbp-2Dh] BYREF
  __int128 v16; // [rsp+78h] [rbp-29h] BYREF
  __int64 v17; // [rsp+88h] [rbp-19h]
  _BYTE v18[64]; // [rsp+98h] [rbp-9h] BYREF
  const unsigned __int16 *v19; // [rsp+108h] [rbp+67h] BYREF

  v19 = a1;
  v16 = 0;
  v17 = 0;
  v7 = CoInitialize(0);
  v14 = v7;
  v13 = 0;
  v12 = &Dfdll::CIUnknownBasedPointer<IDispatch>::`vftable';
  v8 = BindToServer(&CLSID_DeploymentServiceCom, &IID_IDispatch, &v13);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(void *, GUID *, const unsigned __int16 **, __int64, int, unsigned int *))(*(_QWORD *)v13 + 40LL))(
           v13,
           &GUID_NULL,
           &v19,
           1,
           2048,
           &v11);
    if ( v8 >= 0 )
    {
      LODWORD(v17) = a3;
      *(_QWORD *)&v16 = a2;
      LOWORD(v10) = 1;
      v8 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64, int, __int128 *, char *, _BYTE *, _BYTE *))(*(_QWORD *)v13 + 48LL))(
             v13,
             v11,
             &GUID_NULL,
             2048,
             v10,
             &v16,
             (char *)a4 + 8,
             v18,
             v15);
    }
  }
  v12 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v13 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( !v7 )
    CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007928  mov     rax, rsp
0x18000792b  mov     [rax+10h], rbx
0x18000792f  mov     [rax+18h], rsi
0x180007933  mov     [rax+8], rcx
0x180007937  push    rbp
0x180007938  push    rdi
0x180007939  push    r13
0x18000793b  push    r14
0x18000793d  push    r15
0x18000793f  lea     rbp, [rax-5Fh]
0x180007943  sub     rsp, 0D0h
0x18000794a  mov     rsi, r9
0x18000794d  mov     r14d, r8d
0x180007950  mov     r15, rdx
0x180007953  xorps   xmm0, xmm0
0x180007956  xor     eax, eax
0x180007958  movups  [rbp+57h+var_80], xmm0
0x18000795c  mov     [rbp+57h+var_70], rax
0x180007960  xor     ecx, ecx; pvReserved
0x180007962  call    cs:__imp_CoInitialize
0x180007968  mov     ebx, eax
0x18000796a  mov     [rbp+57h+var_88], eax
0x18000796d  and     [rbp+57h+var_90], 0
0x180007972  lea     rax, ??_7?$CIUnknownBasedPointer@UIDispatch@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDispatch>::`vftable'
0x180007979  mov     [rbp+57h+var_98], rax
0x18000797d  lea     r8, [rbp+57h+var_90]; void **
0x180007981  lea     rdx, IID_IDispatch; struct _GUID *
0x180007988  lea     rcx, ?CLSID_DeploymentServiceCom@@3U_GUID@@A; struct _GUID *
0x18000798f  call    BindToServer
0x180007994  mov     edi, eax
0x180007996  test    eax, eax
0x180007998  js      loc_180007A2F
0x18000799e  mov     rcx, [rbp+57h+var_90]
0x1800079a2  mov     rax, [rcx]
0x1800079a5  lea     rdx, [rbp+57h+var_A0]
0x1800079a9  mov     [rsp+0F0h+var_C8], rdx
0x1800079ae  mov     dword ptr [rsp+0F0h+var_D0], 800h
0x1800079b6  mov     r13d, 1
0x1800079bc  mov     r9d, r13d
0x1800079bf  lea     r8, [rbp+57h+arg_0]
0x1800079c3  lea     rdx, GUID_NULL
0x1800079ca  mov     rax, [rax+28h]
0x1800079ce  call    cs:__guard_dispatch_icall_fptr
0x1800079d4  mov     edi, eax
0x1800079d6  test    eax, eax
0x1800079d8  js      short loc_180007A2F
0x1800079da  mov     dword ptr [rbp+57h+var_70], r14d
0x1800079de  mov     qword ptr [rbp+57h+var_80], r15
0x1800079e2  mov     rcx, [rbp+57h+var_90]
0x1800079e6  mov     rax, [rcx]
0x1800079e9  lea     rdx, [rsi+8]
0x1800079ed  lea     r10, [rbp+57h+var_84]
0x1800079f1  mov     [rsp+0F0h+var_B0], r10
0x1800079f6  lea     r10, [rbp+57h+var_60]
0x1800079fa  mov     [rsp+0F0h+var_B8], r10
0x1800079ff  mov     [rsp+0F0h+var_C0], rdx
0x180007a04  lea     rdx, [rbp+57h+var_80]
0x180007a08  mov     [rsp+0F0h+var_C8], rdx
0x180007a0d  mov     word ptr [rsp+0F0h+var_D0], r13w
0x180007a13  mov     r9d, 800h
0x180007a19  lea     r8, GUID_NULL
0x180007a20  mov     edx, [rbp+57h+var_A0]
0x180007a23  mov     rax, [rax+30h]
0x180007a27  call    cs:__guard_dispatch_icall_fptr
0x180007a2d  mov     edi, eax
0x180007a2f  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180007a36  mov     [rbp+57h+var_98], rax
0x180007a3a  mov     rcx, [rbp+57h+var_90]
0x180007a3e  test    rcx, rcx
0x180007a41  jz      short loc_180007A51
0x180007a43  mov     rax, [rcx]
0x180007a46  mov     rax, [rax+10h]
0x180007a4a  call    cs:__guard_dispatch_icall_fptr
0x180007a50  nop
0x180007a51  test    ebx, ebx
0x180007a53  jnz     short loc_180007A5C
0x180007a55  call    cs:__imp_CoUninitialize
0x180007a5b  nop
0x180007a5c  mov     eax, edi
0x180007a5e  lea     r11, [rsp+0F0h+var_20]
0x180007a66  mov     rbx, [r11+38h]
0x180007a6a  mov     rsi, [r11+40h]
0x180007a6e  mov     rsp, r11
0x180007a71  pop     r15
0x180007a73  pop     r14
0x180007a75  pop     r13
0x180007a77  pop     rdi
0x180007a78  pop     rbp
0x180007a79  retn
```
