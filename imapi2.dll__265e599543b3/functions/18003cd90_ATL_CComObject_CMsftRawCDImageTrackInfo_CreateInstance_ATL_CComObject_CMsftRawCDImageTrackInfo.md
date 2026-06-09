# ATL::CComObject<CMsftRawCDImageTrackInfo>::CreateInstance(ATL::CComObject<CMsftRawCDImageTrackInfo> * *)

- ea: `0x18003cd90`
- end: `0x18003ce65`
- name: `?CreateInstance@?$CComObject@VCMsftRawCDImageTrackInfo@@@ATL@@SAJPEAPEAV12@@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003ebf0`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x18003c09c`
- `0x18003cd90`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsftRawCDImageTrackInfo>::CreateInstance(CMsftRawCDImageTrackInfo **a1)
{
  CMsftRawCDImageTrackInfo *v3; // rax
  CMsftRawCDImageTrackInfo *v4; // rbx
  struct ATL::CAtlModule *v5; // rcx
  int v6; // eax
  unsigned int v7; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (CMsftRawCDImageTrackInfo *)operator new(0x58u);
  v4 = v3;
  if ( !v3 )
  {
    v7 = -2147024882;
    goto LABEL_12;
  }
  CMsftRawCDImageTrackInfo::CMsftRawCDImageTrackInfo(v3);
  *(_QWORD *)v4 = &ATL::CComObject<CMsftRawCDImageTrackInfo>::`vftable'{for `ATL::IDispatchImpl<IRawCDImageTrackInfo,&_GUID const IID_IRawCDImageTrackInfo,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  v5 = ATL::_pAtlModule;
  *((_QWORD *)v4 + 1) = &ATL::CComObject<CMsftRawCDImageTrackInfo>::`vftable'{for `ISupportErrorInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
  ATL::SafeIncrementReferenceMultiThread((volatile int *)v4 + 4);
  v6 = ATL::CComSafeDeleteCriticalSection::Init((CMsftRawCDImageTrackInfo *)((char *)v4 + 24));
  if ( v6 >= 0 )
  {
    *((_QWORD *)v4 + 9) = 0;
    v6 = 0;
    *((_DWORD *)v4 + 20) = -1023;
  }
  v7 = 0;
  if ( v6 < 0 )
    v7 = v6;
  ATL::SafeDecrementReferenceMultiThread((volatile int *)v4 + 4);
  if ( v7 )
  {
    (*(void (__fastcall **)(CMsftRawCDImageTrackInfo *, __int64))(*(_QWORD *)v4 + 160LL))(v4, 1);
LABEL_12:
    v4 = 0;
    goto LABEL_13;
  }
  v7 = 0;
LABEL_13:
  *a1 = v4;
  return v7;
}

```

## disassembly

```asm
0x18003cd90  push    rbx
0x18003cd92  push    rbp
0x18003cd93  push    rsi
0x18003cd94  push    rdi
0x18003cd95  sub     rsp, 28h
0x18003cd99  mov     rsi, rcx
0x18003cd9c  test    rcx, rcx
0x18003cd9f  jnz     short loc_18003CDAB
0x18003cda1  mov     eax, 80004003h
0x18003cda6  jmp     loc_18003CE5C
0x18003cdab  mov     qword ptr [rcx], 0
0x18003cdb2  mov     ecx, 58h ; 'X'; Size
0x18003cdb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cdbc  mov     rbx, rax
0x18003cdbf  test    rax, rax
0x18003cdc2  jz      loc_18003CE50
0x18003cdc8  mov     rcx, rax; this
0x18003cdcb  call    ??0CMsftRawCDImageTrackInfo@@QEAA@XZ; CMsftRawCDImageTrackInfo::CMsftRawCDImageTrackInfo(void)
0x18003cdd0  lea     rcx, ??_7?$CComObject@VCMsftRawCDImageTrackInfo@@@ATL@@6B?$IDispatchImpl@UIRawCDImageTrackInfo@@$1?IID_IRawCDImageTrackInfo@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMsftRawCDImageTrackInfo>::`vftable'{for `ATL::IDispatchImpl<IRawCDImageTrackInfo,&_GUID const IID_IRawCDImageTrackInfo,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18003cdd7  mov     [rbx], rcx
0x18003cdda  lea     rax, ??_7?$CComObject@VCMsftRawCDImageTrackInfo@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMsftRawCDImageTrackInfo>::`vftable'{for `ISupportErrorInfo'}
0x18003cde1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003cde8  mov     [rbx+8], rax
0x18003cdec  mov     rax, [rcx]
0x18003cdef  mov     rax, [rax+8]
0x18003cdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdf8  lea     rcx, [rbx+10h]; volatile int *
0x18003cdfc  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18003ce01  lea     rcx, [rbx+18h]; this
0x18003ce05  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18003ce0a  test    eax, eax
0x18003ce0c  js      short loc_18003CE1F
0x18003ce0e  mov     qword ptr [rbx+48h], 0
0x18003ce16  xor     eax, eax
0x18003ce18  mov     dword ptr [rbx+50h], 0FFFFFC01h
0x18003ce1f  xor     edi, edi
0x18003ce21  lea     rcx, [rbx+10h]; volatile int *
0x18003ce25  test    eax, eax
0x18003ce27  cmovs   edi, eax
0x18003ce2a  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18003ce2f  test    edi, edi
0x18003ce31  jz      short loc_18003CE4C
0x18003ce33  mov     rax, [rbx]
0x18003ce36  mov     edx, 1
0x18003ce3b  mov     rcx, rbx
0x18003ce3e  mov     rax, [rax+0A0h]
0x18003ce45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce4a  jmp     short loc_18003CE55
0x18003ce4c  xor     edi, edi
0x18003ce4e  jmp     short loc_18003CE57
0x18003ce50  mov     edi, 8007000Eh
0x18003ce55  xor     ebx, ebx
0x18003ce57  mov     [rsi], rbx
0x18003ce5a  mov     eax, edi
0x18003ce5c  add     rsp, 28h
0x18003ce60  pop     rdi
0x18003ce61  pop     rsi
0x18003ce62  pop     rbp
0x18003ce63  pop     rbx
0x18003ce64  retn
```
