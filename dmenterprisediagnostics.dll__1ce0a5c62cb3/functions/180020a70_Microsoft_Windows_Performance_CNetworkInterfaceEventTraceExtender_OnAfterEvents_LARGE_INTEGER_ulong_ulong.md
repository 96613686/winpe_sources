# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180020a70`
- end: `0x180020c20`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `432`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x18000b1e0`
- `0x18001872c`
- `0x180018998`
- `0x180020a70`
- `0x180026010`

## string_xrefs

- `0x180020a95`: `Iphlpapi.dll`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  FARPROC v8; // rax
  unsigned int i; // edi
  unsigned int *v10; // rsi
  __int64 v11; // rcx
  int v12; // esi
  FARPROC v13; // rax
  unsigned int *v15; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-C8h] BYREF
  char v17; // [rsp+50h] [rbp-B0h]
  _QWORD v18[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v19; // [rsp+70h] [rbp-90h]
  _QWORD v20[3]; // [rsp+78h] [rbp-88h] BYREF
  char v21; // [rsp+90h] [rbp-70h]
  _WORD v22[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v23; // [rsp+A4h] [rbp-5Ch]
  union _LARGE_INTEGER v24; // [rsp+B0h] [rbp-50h]
  struct _GUID v25; // [rsp+B8h] [rbp-48h]
  unsigned int *v26; // [rsp+E8h] [rbp-18h]
  int v27; // [rsp+F0h] [rbp-10h]
  unsigned int v28; // [rsp+F4h] [rbp-Ch]

  v16[0] = 0;
  v16[1] = L"Iphlpapi.dll";
  v16[2] = 0;
  v18[0] = v16;
  v17 = 0;
  v18[1] = "GetIfTable2Ex";
  v18[2] = 0;
  v20[0] = v16;
  v19 = 0;
  v20[1] = "FreeMibTable";
  v20[2] = 0;
  v21 = 0;
  if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)v18) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)v20) )
    {
      v15 = 0;
      v8 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)v18);
      if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int **))v8)(0, &v15) )
      {
        for ( i = 0; ; ++i )
        {
          v10 = v15;
          if ( i >= *v15 )
            break;
          memset_0(v22, 0, 0x58u);
          v11 = *((_QWORD *)this + 2);
          v22[0] = a4;
          v24 = a2;
          v25 = SystemConfigExGuid;
          v23 = 36;
          v27 = 1352;
          v28 = a3;
          v26 = &v10[338 * i + 2];
          v12 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, v22, 0, 0);
          if ( v12 < 0 )
            goto LABEL_10;
        }
        v13 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)v20);
        ((void (__fastcall *)(unsigned int *))v13)(v15);
      }
    }
  }
  v12 = Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(this, a2, a3, a4);
LABEL_10:
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(v16);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180020a70  push    rbp
0x180020a72  push    rbx
0x180020a73  push    rsi
0x180020a74  push    rdi
0x180020a75  push    r12
0x180020a77  push    r14
0x180020a79  push    r15
0x180020a7b  lea     rbp, [rsp-10h]
0x180020a80  sub     rsp, 110h
0x180020a87  mov     rax, cs:__security_cookie
0x180020a8e  xor     rax, rsp
0x180020a91  mov     [rbp+40h+var_40], rax
0x180020a95  lea     rax, aIphlpapiDll; "Iphlpapi.dll"
0x180020a9c  mov     [rsp+140h+var_108], 0
0x180020aa5  mov     [rsp+140h+var_100], rax
0x180020aaa  mov     r14, rcx
0x180020aad  lea     rax, [rsp+140h+var_108]
0x180020ab2  mov     [rsp+140h+var_F8], 0
0x180020abb  mov     [rsp+140h+var_E8], rax
0x180020ac0  lea     rcx, [rsp+140h+var_E8]
0x180020ac5  lea     rax, aGetiftable2ex; "GetIfTable2Ex"
0x180020acc  mov     [rsp+140h+var_F0], 0
0x180020ad1  mov     [rsp+140h+var_E0], rax
0x180020ad6  mov     r12d, r9d
0x180020ad9  lea     rax, [rsp+140h+var_108]
0x180020ade  mov     [rsp+140h+var_D8], 0
0x180020ae7  mov     [rsp+140h+var_C8], rax
0x180020aec  mov     r15d, r8d
0x180020aef  lea     rax, aFreemibtable; "FreeMibTable"
0x180020af6  mov     [rsp+140h+var_D0], 0
0x180020afb  mov     [rbp+40h+var_C0], rax
0x180020aff  mov     rbx, rdx
0x180020b02  mov     [rbp+40h+var_B8], 0
0x180020b0a  mov     [rbp+40h+var_B0], 0
0x180020b0e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180020b13  test    rax, rax
0x180020b16  jz      loc_180020BE3
0x180020b1c  lea     rcx, [rsp+140h+var_C8]
0x180020b21  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180020b26  test    rax, rax
0x180020b29  jz      loc_180020BE3
0x180020b2f  lea     rcx, [rsp+140h+var_E8]
0x180020b34  mov     [rsp+140h+var_110], 0
0x180020b3d  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180020b42  lea     rdx, [rsp+140h+var_110]
0x180020b47  xor     ecx, ecx
0x180020b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b4e  test    eax, eax
0x180020b50  jnz     loc_180020BE3
0x180020b56  xor     edi, edi
0x180020b58  mov     rsi, [rsp+140h+var_110]
0x180020b5d  cmp     edi, [rsi]
0x180020b5f  jnb     short loc_180020BCF
0x180020b61  xor     edx, edx; Val
0x180020b63  lea     rcx, [rbp+40h+var_A0]; void *
0x180020b67  lea     r8d, [rdx+58h]; Size
0x180020b6b  call    memset_0
0x180020b70  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x180020b77  mov     rcx, [r14+10h]
0x180020b7b  lea     rdx, [rbp+40h+var_A0]
0x180020b7f  mov     [rbp+40h+var_A0], r12w
0x180020b84  xor     r9d, r9d
0x180020b87  mov     [rbp+40h+var_90], rbx
0x180020b8b  xor     r8d, r8d
0x180020b8e  movdqu  [rbp+40h+var_88], xmm0
0x180020b93  mov     [rbp+40h+var_9C], 24h ; '$'
0x180020b97  mov     [rbp+40h+var_50], 548h
0x180020b9e  mov     [rbp+40h+var_4C], r15d
0x180020ba2  mov     eax, edi
0x180020ba4  imul    rax, 548h
0x180020bab  add     rax, 8
0x180020baf  add     rax, rsi
0x180020bb2  mov     [rbp+40h+var_58], rax
0x180020bb6  mov     rax, [rcx]
0x180020bb9  mov     rax, [rax+0C0h]
0x180020bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bc5  mov     esi, eax
0x180020bc7  test    eax, eax
0x180020bc9  js      short loc_180020BF6
0x180020bcb  inc     edi
0x180020bcd  jmp     short loc_180020B58
0x180020bcf  lea     rcx, [rsp+140h+var_C8]
0x180020bd4  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180020bd9  mov     rcx, [rsp+140h+var_110]
0x180020bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be3  mov     r9d, r12d; unsigned int
0x180020be6  mov     r8d, r15d; unsigned int
0x180020be9  mov     rdx, rbx; union _LARGE_INTEGER
0x180020bec  mov     rcx, r14; this
0x180020bef  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x180020bf4  mov     esi, eax
0x180020bf6  lea     rcx, [rsp+140h+var_108]
0x180020bfb  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180020c00  mov     eax, esi
0x180020c02  mov     rcx, [rbp+40h+var_40]
0x180020c06  xor     rcx, rsp; StackCookie
0x180020c09  call    __security_check_cookie
0x180020c0e  add     rsp, 110h
0x180020c15  pop     r15
0x180020c17  pop     r14
0x180020c19  pop     r12
0x180020c1b  pop     rdi
0x180020c1c  pop     rsi
0x180020c1d  pop     rbx
0x180020c1e  pop     rbp
0x180020c1f  retn
```
