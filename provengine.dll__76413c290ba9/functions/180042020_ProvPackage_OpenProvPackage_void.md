# ProvPackage::OpenProvPackage(void)

- ea: `0x180042020`
- end: `0x180042304`
- name: `?OpenProvPackage@ProvPackage@@UEAA_NXZ`
- size: `740`
- prototype: `char __fastcall(ProvPackage *this, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x18000109c`
- `0x1800010c8`
- `0x1800011ac`
- `0x180001300`
- `0x1800018ec`
- `0x1800071a4`
- `0x18000b030`
- `0x18000b140`
- `0x180021cf4`
- `0x180042020`
- `0x1800433e4`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800420ec`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800420ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ProvPackage::OpenProvPackage(ProvPackage *this, __int64 a2, __int64 a3, int a4)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _QWORD *v7; // rcx
  int v8; // esi
  _QWORD *v9; // rcx
  int v10; // r9d
  int v12; // ebx
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // r9d
  unsigned int v21; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  int v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  _WORD *v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[40]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD Src[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v5 = (_QWORD *)((char *)this + 8);
  if ( (unsigned int)dword_18005A000 > 5 )
  {
    if ( *((_QWORD *)this + 4) < 8u )
      v6 = (char *)this + 8;
    else
      v6 = (char *)*v5;
    *(_QWORD *)v23 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18005A000,
      (unsigned int)&dword_180050984,
      0,
      a4,
      (__int64)v23);
  }
  if ( !v5[2] )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &word_180050926, 0, 0, 2, v26);
    return 0;
  }
  v24 = 0;
  if ( v5[3] < 8u )
    v7 = v5;
  else
    v7 = (_QWORD *)*v5;
  v8 = OpenProvisioningPackageForRead(v7, &v24);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
    {
      v23[0] = v8;
      v18 = std::wstring::c_str(v5);
      v19 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v25, v18);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)&unk_180050948,
        0,
        v20,
        v19,
        (__int64)v23);
    }
    v21 = wil::verify_hresult<long>((unsigned int)v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v21,
      v22);
  }
  if ( v5[3] < 8u )
    v9 = v5;
  else
    v9 = (_QWORD *)*v5;
  if ( !(unsigned __int8)Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(
                           v9,
                           (char *)this + 112) )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      if ( v5[3] >= 8u )
        v5 = (_QWORD *)*v5;
      *(_QWORD *)v23 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)&dword_1800508E4,
        0,
        v10,
        (__int64)v23);
    }
    return 0;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v24 + 8LL))(v24, Src, 260);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
    {
      v23[0] = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)&byte_180050877,
        0,
        0,
        (__int64)v23);
    }
    v17 = wil::verify_hresult<long>((unsigned int)v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v17,
      v22);
  }
  if ( (unsigned int)dword_18005A000 > 4 )
  {
    v23[0] = v12;
    v25 = Src;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18005A000,
      (unsigned int)byte_1800508AD,
      0,
      v13,
      (__int64)&v25,
      (__int64)v23);
  }
  if ( Src[0] )
  {
    v14 = -1;
    do
      ++v14;
    while ( Src[v14] );
  }
  std::wstring::assign((char *)this + 72, Src);
  v15 = v24;
  v16 = *((_QWORD *)this + 13);
  if ( v24 != v16 )
  {
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 128LL))(v16);
    *((_QWORD *)this + 13) = v15;
  }
  return 1;
}

```

## disassembly

```asm
0x180042020  push    rbp
0x180042022  push    rbx
0x180042023  push    rsi
0x180042024  push    rdi
0x180042025  push    r14
0x180042027  push    r15
0x180042029  lea     rbp, [rsp-198h]
0x180042031  sub     rsp, 298h
0x180042038  mov     rax, cs:__security_cookie
0x18004203f  xor     rax, rsp
0x180042042  mov     [rbp+1C0h+var_40], rax
0x180042049  mov     rdi, rcx
0x18004204c  mov     eax, cs:dword_18005A000
0x180042052  lea     rbx, [rcx+8]
0x180042056  lea     r15, dword_18005A000
0x18004205d  cmp     eax, 5
0x180042060  jbe     short loc_180042092
0x180042062  cmp     qword ptr [rbx+18h], 8
0x180042067  jb      short loc_18004206E
0x180042069  mov     rax, [rbx]
0x18004206c  jmp     short loc_180042071
0x18004206e  mov     rax, rbx
0x180042071  mov     qword ptr [rsp+2C0h+var_290], rax
0x180042076  lea     rax, [rsp+2C0h+var_290]
0x18004207b  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180042080  xor     r8d, r8d
0x180042083  lea     rdx, dword_180050984
0x18004208a  mov     rcx, r15
0x18004208d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180042092  xor     r14d, r14d
0x180042095  cmp     [rbx+10h], r14
0x180042099  jnz     short loc_1800420D3
0x18004209b  mov     eax, cs:dword_18005A000
0x1800420a1  cmp     eax, 3
0x1800420a4  jbe     loc_18004214E
0x1800420aa  lea     rax, [rsp+2C0h+var_278]
0x1800420af  mov     [rsp+2C0h+var_298], rax
0x1800420b4  mov     [rsp+2C0h+var_2A0], 2
0x1800420bc  xor     r9d, r9d
0x1800420bf  xor     r8d, r8d
0x1800420c2  lea     rdx, word_180050926
0x1800420c9  mov     rcx, r15
0x1800420cc  call    _tlgWriteTransfer_EventWriteTransfer
0x1800420d1  jmp     short loc_18004214E
0x1800420d3  mov     [rsp+2C0h+var_288], r14
0x1800420d8  cmp     qword ptr [rbx+18h], 8
0x1800420dd  jb      short loc_1800420E4
0x1800420df  mov     rcx, [rbx]
0x1800420e2  jmp     short loc_1800420E7
0x1800420e4  mov     rcx, rbx
0x1800420e7  lea     rdx, [rsp+2C0h+var_288]
0x1800420ec  call    cs:__imp_OpenProvisioningPackageForRead
0x1800420f2  mov     esi, eax
0x1800420f4  test    eax, eax
0x1800420f6  js      loc_18004228E
0x1800420fc  cmp     qword ptr [rbx+18h], 8
0x180042101  jb      short loc_180042108
0x180042103  mov     rcx, [rbx]
0x180042106  jmp     short loc_18004210B
0x180042108  mov     rcx, rbx
0x18004210b  lea     rdx, [rdi+70h]
0x18004210f  call    ?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x180042114  test    al, al
0x180042116  jnz     short loc_180042155
0x180042118  mov     eax, cs:dword_18005A000
0x18004211e  cmp     eax, 2
0x180042121  jbe     short loc_18004214E
0x180042123  cmp     qword ptr [rbx+18h], 8
0x180042128  jb      short loc_18004212D
0x18004212a  mov     rbx, [rbx]
0x18004212d  mov     qword ptr [rsp+2C0h+var_290], rbx
0x180042132  lea     rax, [rsp+2C0h+var_290]
0x180042137  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18004213c  xor     r8d, r8d
0x18004213f  lea     rdx, dword_1800508E4
0x180042146  mov     rcx, r15
0x180042149  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004214e  xor     al, al
0x180042150  jmp     loc_180042210
0x180042155  mov     rcx, [rsp+2C0h+var_288]
0x18004215a  mov     rax, [rcx]
0x18004215d  mov     r8d, 104h
0x180042163  lea     rdx, [rsp+2C0h+Src]
0x180042168  mov     rax, [rax+8]
0x18004216c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042171  mov     ebx, eax
0x180042173  test    eax, eax
0x180042175  js      loc_18004222F
0x18004217b  mov     eax, cs:dword_18005A000
0x180042181  cmp     eax, 4
0x180042184  jbe     short loc_1800421BA
0x180042186  mov     [rsp+2C0h+var_290], ebx
0x18004218a  lea     rax, [rsp+2C0h+Src]
0x18004218f  mov     [rsp+2C0h+var_280], rax
0x180042194  lea     rax, [rsp+2C0h+var_290]
0x180042199  mov     [rsp+2C0h+var_298], rax
0x18004219e  lea     rax, [rsp+2C0h+var_280]
0x1800421a3  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x1800421a8  xor     r8d, r8d
0x1800421ab  lea     rdx, byte_1800508AD
0x1800421b2  mov     rcx, r15
0x1800421b5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800421ba  cmp     [rsp+2C0h+Src], r14w
0x1800421c0  jnz     short loc_1800421C7
0x1800421c2  mov     r8, r14
0x1800421c5  jmp     short loc_1800421DA
0x1800421c7  lea     rax, [rsp+2C0h+Src]
0x1800421cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800421d0  inc     r8
0x1800421d3  cmp     [rax+r8*2], r14w
0x1800421d8  jnz     short loc_1800421D0
0x1800421da  lea     rcx, [rdi+48h]; void *
0x1800421de  lea     rdx, [rsp+2C0h+Src]; Src
0x1800421e3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800421e8  mov     rbx, [rsp+2C0h+var_288]
0x1800421ed  mov     rcx, [rdi+68h]
0x1800421f1  cmp     rbx, rcx
0x1800421f4  jz      short loc_18004220E
0x1800421f6  test    rcx, rcx
0x1800421f9  jz      short loc_18004220A
0x1800421fb  mov     rax, [rcx]
0x1800421fe  mov     rax, [rax+80h]
0x180042205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004220a  mov     [rdi+68h], rbx
0x18004220e  mov     al, 1
0x180042210  mov     rcx, [rbp+1C0h+var_40]
0x180042217  xor     rcx, rsp; StackCookie
0x18004221a  call    __security_check_cookie
0x18004221f  add     rsp, 298h
0x180042226  pop     r15
0x180042228  pop     r14
0x18004222a  pop     rdi
0x18004222b  pop     rsi
0x18004222c  pop     rbx
0x18004222d  pop     rbp
0x18004222e  retn
0x18004222f  mov     ecx, cs:dword_18005A000
0x180042235  cmp     ecx, 2
0x180042238  jbe     short loc_18004226B
0x18004223a  xor     edx, edx
0x18004223c  mov     rcx, r15
0x18004223f  call    _tlgKeywordOn
0x180042244  test    al, al
0x180042246  jz      short loc_18004226B
0x180042248  mov     [rsp+2C0h+var_290], ebx
0x18004224c  lea     rax, [rsp+2C0h+var_290]
0x180042251  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180042256  xor     r9d, r9d
0x180042259  xor     r8d, r8d
0x18004225c  lea     rdx, byte_180050877
0x180042263  mov     rcx, r15
0x180042266  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004226b  mov     ecx, ebx
0x18004226d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180042272  mov     r9d, eax; char *
0x180042275  mov     rcx, [rbp+1C8h]; this
0x18004227c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180042283  mov     edx, 83h; void *
0x180042288  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004228e  mov     edx, cs:dword_18005A000
0x180042294  cmp     edx, 2
0x180042297  jbe     short loc_1800422E1
0x180042299  xor     edx, edx
0x18004229b  mov     rcx, r15
0x18004229e  call    _tlgKeywordOn
0x1800422a3  test    al, al
0x1800422a5  jz      short loc_1800422E1
0x1800422a7  mov     [rsp+2C0h+var_290], esi
0x1800422ab  mov     rcx, rbx
0x1800422ae  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800422b3  mov     rdx, rax
0x1800422b6  lea     rcx, [rsp+2C0h+var_280]
0x1800422bb  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x1800422c0  lea     rcx, [rsp+2C0h+var_290]
0x1800422c5  mov     [rsp+2C0h+var_298], rcx
0x1800422ca  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x1800422cf  xor     r8d, r8d
0x1800422d2  lea     rdx, unk_180050948
0x1800422d9  mov     rcx, r15
0x1800422dc  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800422e1  mov     ecx, esi
0x1800422e3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800422e8  mov     r9d, eax; char *
0x1800422eb  mov     rcx, [rbp+1C8h]; this
0x1800422f2  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800422f9  mov     edx, 71h ; 'q'; void *
0x1800422fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
