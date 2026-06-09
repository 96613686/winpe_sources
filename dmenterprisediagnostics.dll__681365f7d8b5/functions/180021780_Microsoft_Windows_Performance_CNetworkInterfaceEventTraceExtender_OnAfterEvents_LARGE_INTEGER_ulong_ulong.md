# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x180021780`
- end: `0x180021931`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `433`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x18000b750`
- `0x180019030`
- `0x18001934c`
- `0x180021780`
- `0x180027010`

## string_xrefs

- `0x1800217a5`: `Iphlpapi.dll`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int (__fastcall *v8)(_QWORD, unsigned int **); // rax
  unsigned int i; // edi
  unsigned int *v10; // rsi
  __int64 v11; // rcx
  int v12; // esi
  void (__fastcall *v13)(unsigned int *); // rax
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
  if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v18) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v20) )
    {
      v15 = 0;
      v8 = (unsigned int (__fastcall *)(_QWORD, unsigned int **))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v18);
      if ( !v8(0, &v15) )
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
        v13 = (void (__fastcall *)(unsigned int *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v20);
        v13(v15);
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
0x180021780  push    rbp
0x180021782  push    rbx
0x180021783  push    rsi
0x180021784  push    rdi
0x180021785  push    r12
0x180021787  push    r14
0x180021789  push    r15
0x18002178b  lea     rbp, [rsp-10h]
0x180021790  sub     rsp, 110h
0x180021797  mov     rax, cs:__security_cookie
0x18002179e  xor     rax, rsp
0x1800217a1  mov     [rbp+40h+var_40], rax
0x1800217a5  lea     rax, aIphlpapiDll; "Iphlpapi.dll"
0x1800217ac  mov     [rsp+140h+var_108], 0
0x1800217b5  mov     [rsp+140h+var_100], rax
0x1800217ba  mov     r14, rcx
0x1800217bd  lea     rax, [rsp+140h+var_108]
0x1800217c2  mov     [rsp+140h+var_F8], 0
0x1800217cb  mov     [rsp+140h+var_E8], rax
0x1800217d0  lea     rcx, [rsp+140h+var_E8]
0x1800217d5  lea     rax, aGetiftable2ex; "GetIfTable2Ex"
0x1800217dc  mov     [rsp+140h+var_F0], 0
0x1800217e1  mov     [rsp+140h+var_E0], rax
0x1800217e6  mov     r12d, r9d
0x1800217e9  lea     rax, [rsp+140h+var_108]
0x1800217ee  mov     [rsp+140h+var_D8], 0
0x1800217f7  mov     [rsp+140h+var_C8], rax
0x1800217fc  mov     r15d, r8d
0x1800217ff  lea     rax, aFreemibtable; "FreeMibTable"
0x180021806  mov     [rsp+140h+var_D0], 0
0x18002180b  mov     [rbp+40h+var_C0], rax
0x18002180f  mov     rbx, rdx
0x180021812  mov     [rbp+40h+var_B8], 0
0x18002181a  mov     [rbp+40h+var_B0], 0
0x18002181e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180021823  test    rax, rax
0x180021826  jz      loc_1800218F3
0x18002182c  lea     rcx, [rsp+140h+var_C8]
0x180021831  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180021836  test    rax, rax
0x180021839  jz      loc_1800218F3
0x18002183f  lea     rcx, [rsp+140h+var_E8]
0x180021844  mov     [rsp+140h+var_110], 0
0x18002184d  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180021852  lea     rdx, [rsp+140h+var_110]
0x180021857  xor     ecx, ecx
0x180021859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002185e  test    eax, eax
0x180021860  jnz     loc_1800218F3
0x180021866  xor     edi, edi
0x180021868  mov     rsi, [rsp+140h+var_110]
0x18002186d  cmp     edi, [rsi]
0x18002186f  jnb     short loc_1800218DF
0x180021871  xor     edx, edx; Val
0x180021873  lea     rcx, [rbp+40h+var_A0]; void *
0x180021877  lea     r8d, [rdx+58h]; Size
0x18002187b  call    memset_0
0x180021880  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x180021887  mov     rcx, [r14+10h]
0x18002188b  lea     rdx, [rbp+40h+var_A0]
0x18002188f  mov     [rbp+40h+var_A0], r12w
0x180021894  xor     r9d, r9d
0x180021897  mov     [rbp+40h+var_90], rbx
0x18002189b  xor     r8d, r8d
0x18002189e  movdqu  [rbp+40h+var_88], xmm0
0x1800218a3  mov     [rbp+40h+var_9C], 24h ; '$'
0x1800218a7  mov     [rbp+40h+var_50], 548h
0x1800218ae  mov     [rbp+40h+var_4C], r15d
0x1800218b2  mov     eax, edi
0x1800218b4  imul    rax, 548h
0x1800218bb  add     rax, 8
0x1800218bf  add     rax, rsi
0x1800218c2  mov     [rbp+40h+var_58], rax
0x1800218c6  mov     rax, [rcx]
0x1800218c9  mov     rax, [rax+0C0h]
0x1800218d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218d5  mov     esi, eax
0x1800218d7  test    eax, eax
0x1800218d9  js      short loc_180021906
0x1800218db  inc     edi
0x1800218dd  jmp     short loc_180021868
0x1800218df  lea     rcx, [rsp+140h+var_C8]
0x1800218e4  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800218e9  mov     rcx, [rsp+140h+var_110]
0x1800218ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218f3  mov     r9d, r12d; unsigned int
0x1800218f6  mov     r8d, r15d; unsigned int
0x1800218f9  mov     rdx, rbx; union _LARGE_INTEGER
0x1800218fc  mov     rcx, r14; this
0x1800218ff  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x180021904  mov     esi, eax
0x180021906  lea     rcx, [rsp+140h+var_108]
0x18002190b  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180021910  mov     eax, esi
0x180021912  mov     rcx, [rbp+40h+var_40]
0x180021916  xor     rcx, rsp; StackCookie
0x180021919  call    __security_check_cookie
0x18002191e  add     rsp, 110h
0x180021925  pop     r15
0x180021927  pop     r14
0x180021929  pop     r12
0x18002192b  pop     rdi
0x18002192c  pop     rsi
0x18002192d  pop     rbx
0x18002192e  pop     rbp
0x18002192f  retn
```
