# EapLm::Peer::ThirdPartyDispatcherConfig::QueryUIBlobFromInteractiveUIInputFields(ulong,_EAP_METHOD_TYPE,ulong,ulong,uchar const *,_EAP_INTERACTIVE_UI_DATA const *,ulong *,uchar * *,_EAP_ERROR * *,uchar * *)

- ea: `0x18000e780`
- end: `0x18000e943`
- name: `?QueryUIBlobFromInteractiveUIInputFields@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJKU_EAP_METHOD_TYPE@@KKPEBEPEBU_EAP_INTERACTIVE_UI_DATA@@PEAKPEAPEAEPEAPEAU_EAP_ERROR@@4@Z`
- size: `451`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, unsigned int, struct _EAP_METHOD_TYPE *, unsigned int, unsigned int, const unsigned __int8 *, const struct _EAP_INTERACTIVE_UI_DATA *, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x18000439c`
- `0x18000503c`
- `0x180005894`
- `0x18000e780`
- `0x18000ec84`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::QueryUIBlobFromInteractiveUIInputFields(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        unsigned int a2,
        struct _EAP_METHOD_TYPE *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        const struct _EAP_INTERACTIVE_UI_DATA *a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        struct _EAP_ERROR **a10)
{
  unsigned __int8 **v12; // rbx
  _QWORD *v13; // r9
  unsigned __int8 *v14; // rax
  int *v15; // r9
  struct _EAP_ERROR *v17; // [rsp+40h] [rbp-68h] BYREF
  const ATL::CAtlException *v18; // [rsp+48h] [rbp-60h] BYREF
  const EapHost::EapException *v19; // [rsp+50h] [rbp-58h] BYREF
  const Exception *v20; // [rsp+58h] [rbp-50h] BYREF
  void *Src; // [rsp+60h] [rbp-48h] BYREF
  size_t Size; // [rsp+68h] [rbp-40h]
  _QWORD v23[2]; // [rsp+70h] [rbp-38h] BYREF
  void **v24; // [rsp+80h] [rbp-28h] BYREF
  BYTE type; // [rsp+88h] [rbp-20h]
  __int64 v26; // [rsp+8Ch] [rbp-1Ch]
  DWORD dwAuthorId; // [rsp+98h] [rbp-10h]

  LODWORD(v17) = 0;
  v12 = a9;
  if ( !a9 || !a8 )
    return 2147500035LL;
  v13 = (_QWORD *)*((_QWORD *)this - 12);
  type = a3->eapType.type;
  v26 = *(_QWORD *)&a3->eapType.dwVendorId;
  if ( type != 0xFE )
    v26 = 0;
  try
  {
    v24 = &EapHost::EapMethodType::`vftable';
    dwAuthorId = a3->dwAuthorId;
    EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(v13, (ReferenceCounted *)&a9, (__int64)&v24);
    v23[1] = a5;
    v23[0] = a6;
    Src = 0;
    Size = 0;
    (*((void (__fastcall **)(unsigned __int8 **, _QWORD, _QWORD, _QWORD *, const struct _EAP_INTERACTIVE_UI_DATA *, void **))*a9
     + 10))(
      a9,
      a2,
      a4,
      v23,
      a7,
      &Src);
    if ( Size )
    {
      v14 = (unsigned __int8 *)Copy<TaskAllocator>(Src, Size);
      *v12 = v14;
      if ( !v14 )
        LODWORD(v17) = -2147024882;
    }
    else
    {
      *v12 = 0;
    }
    *a8 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(Size);
    HeapAllocator::Free(Src);
    if ( a9 )
      ReferenceCounted::Release((ReferenceCounted *)a9);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v17) = -2147024882;
    if ( a10 )
      *a10 = 0;
  }
  catch ( const ATL::CAtlException *v18 )
  {
    LODWORD(v17) = *(_DWORD *)v18;
    if ( a10 )
      *a10 = 0;
  }
  catch ( const EapHost::EapException *v19 )
  {
    EapHost::EapException2EapErrorOle(v19, (const struct EapHost::EapException *)a10, &v17, v15);
  }
  catch ( const Exception *v20 )
  {
    EapHost::Exception2EapErrorOle(v20, (const struct Exception *)a10, &v17, v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids,
      *a8,
      (_DWORD)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000e780  mov     r11, rsp
0x18000e783  mov     [r11+8], rbx
0x18000e787  mov     [r11+10h], rsi
0x18000e78b  push    rdi
0x18000e78c  sub     rsp, 0A0h
0x18000e793  mov     edi, r9d
0x18000e796  mov     esi, edx
0x18000e798  mov     dword ptr [rsp+0A8h+var_68], 0
0x18000e7a0  mov     rbx, [rsp+0A8h+arg_40]
0x18000e7a8  test    rbx, rbx
0x18000e7ab  jz      loc_18000E929
0x18000e7b1  cmp     [rsp+0A8h+arg_38], 0
0x18000e7ba  jz      loc_18000E929
0x18000e7c0  mov     r9, [rcx-60h]
0x18000e7c4  mov     cl, [r8]
0x18000e7c7  mov     [r11-20h], cl
0x18000e7cb  mov     eax, [r8+4]
0x18000e7cf  mov     [r11-1Ch], eax
0x18000e7d3  mov     eax, [r8+8]
0x18000e7d7  mov     [r11-18h], eax
0x18000e7db  cmp     cl, 0FEh
0x18000e7de  jz      short loc_18000E7E8
0x18000e7e0  mov     qword ptr [r11-1Ch], 0
0x18000e7e8  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000e7ef  mov     [rsp+0A8h+var_28], rax
0x18000e7f7  mov     eax, [r8+0Ch]
0x18000e7fb  mov     [rsp+0A8h+var_10], eax
0x18000e802  lea     r8, [rsp+0A8h+var_28]
0x18000e80a  lea     rdx, [rsp+0A8h+arg_40]
0x18000e812  mov     rcx, r9
0x18000e815  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000e81a  nop
0x18000e81b  mov     eax, [rsp+0A8h+arg_20]
0x18000e822  mov     [rsp+0A8h+var_30], rax
0x18000e827  mov     rax, [rsp+0A8h+arg_28]
0x18000e82f  mov     [rsp+0A8h+var_38], rax
0x18000e834  mov     [rsp+0A8h+Src], 0
0x18000e83d  mov     [rsp+0A8h+Size], 0
0x18000e846  mov     rcx, [rsp+0A8h+arg_40]
0x18000e84e  mov     rax, [rcx]
0x18000e851  lea     rdx, [rsp+0A8h+Src]
0x18000e856  mov     [rsp+0A8h+var_80], rdx
0x18000e85b  mov     rdx, [rsp+0A8h+arg_30]
0x18000e863  mov     [rsp+0A8h+var_88], rdx
0x18000e868  lea     r9, [rsp+0A8h+var_38]
0x18000e86d  mov     r8d, edi
0x18000e870  mov     edx, esi
0x18000e872  mov     rax, [rax+50h]
0x18000e876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e87b  mov     rdx, [rsp+0A8h+Size]; Size
0x18000e880  test    rdx, rdx
0x18000e883  jz      short loc_18000E8A1
0x18000e885  mov     rcx, [rsp+0A8h+Src]; Src
0x18000e88a  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x18000e88f  mov     [rbx], rax
0x18000e892  test    rax, rax
0x18000e895  jnz     short loc_18000E8A8
0x18000e897  mov     dword ptr [rsp+0A8h+var_68], 8007000Eh
0x18000e89f  jmp     short loc_18000E8A8
0x18000e8a1  mov     qword ptr [rbx], 0
0x18000e8a8  mov     rcx, [rsp+0A8h+Size]
0x18000e8ad  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000e8b2  mov     rcx, [rsp+0A8h+arg_38]
0x18000e8ba  mov     [rcx], eax
0x18000e8bc  mov     rcx, [rsp+0A8h+Src]; void *
0x18000e8c1  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000e8c6  nop
0x18000e8c7  mov     rcx, [rsp+0A8h+arg_40]; this
0x18000e8cf  test    rcx, rcx
0x18000e8d2  jz      short loc_18000E8DA
0x18000e8d4  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000e8d9  nop
0x18000e8da  jmp     short loc_18000E8E2
0x18000e8dc  jmp     short loc_18000E8E2
0x18000e8de  jmp     short loc_18000E8E2
0x18000e8e0  jmp     short $+2
0x18000e8e2  lea     rax, WPP_GLOBAL_Control
0x18000e8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8f0  cmp     rcx, rax
0x18000e8f3  jz      short loc_18000E923
0x18000e8f5  test    byte ptr [rcx+1Ch], 4
0x18000e8f9  jz      short loc_18000E923
0x18000e8fb  mov     edx, 16h
0x18000e900  mov     eax, dword ptr [rsp+0A8h+var_68]
0x18000e904  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000e908  mov     r9, [rsp+0A8h+arg_38]
0x18000e910  mov     r9d, [r9]
0x18000e913  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000e91a  mov     rcx, [rcx+10h]
0x18000e91e  call    WPP_SF_dd
0x18000e923  mov     eax, dword ptr [rsp+0A8h+var_68]
0x18000e927  jmp     short loc_18000E92E
0x18000e929  mov     eax, 80004003h
0x18000e92e  lea     r11, [rsp+0A8h+var_8]
0x18000e936  mov     rbx, [r11+10h]
0x18000e93a  mov     rsi, [r11+18h]
0x18000e93e  mov     rsp, r11
0x18000e941  pop     rdi
0x18000e942  retn
```
