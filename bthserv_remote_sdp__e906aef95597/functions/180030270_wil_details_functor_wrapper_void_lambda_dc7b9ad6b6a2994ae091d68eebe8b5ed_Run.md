# wil::details::functor_wrapper_void__lambda_dc7b9ad6b6a2994ae091d68eebe8b5ed___::Run

- ea: `0x180030270`
- end: `0x18003044b`
- name: `wil::details::functor_wrapper_void__lambda_dc7b9ad6b6a2994ae091d68eebe8b5ed___::Run`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ddb8`

## callees

- `0x180003740`
- `0x180011b9c`
- `0x180012004`
- `0x1800120b8`
- `0x180030270`
- `0x180030f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180030284`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180030284`
- `deviceassociation!DafStartFinalize` at `0x1800302a1`
- `deviceassociation!DafStartFinalize` at `0x1800302a1`

## string_xrefs

- `0x1800303b2`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x180030436`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_dc7b9ad6b6a2994ae091d68eebe8b5ed___::Run(__int64 a1)
{
  unsigned int **v1; // rbx
  int v2; // edx
  int v3; // r8d
  char v4; // dl
  bool v6; // dl
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(unsigned int ***)(a1 + 8);
  ResetEvent(*((HANDLE *)*v1 + 256));
  *v1[1] = DafStartFinalize(
             *((_QWORD *)*v1 + 255),
             &Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_FinalizeCompleteCallback,
             *v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    v7 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v7,
      v9);
  }
  *v1[1] = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)*v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    LOBYTE(v2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v8 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v8,
      v9);
  }
  v4 = 1;
  *((_BYTE *)*v1 + 144) = 1;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  return 0;
}

```

## disassembly

```asm
0x180030270  push    rbx
0x180030272  sub     rsp, 50h
0x180030276  mov     rbx, [rcx+8]
0x18003027a  mov     rcx, [rbx]
0x18003027d  mov     rcx, [rcx+800h]; hEvent
0x180030284  call    cs:__imp_ResetEvent
0x18003028b  nop     dword ptr [rax+rax+00h]
0x180030290  mov     r8, [rbx]
0x180030293  lea     rdx, ?s_FinalizeCompleteCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_FinalizeCompleteCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x18003029a  mov     rcx, [r8+7F8h]
0x1800302a1  call    cs:__imp_DafStartFinalize
0x1800302a8  nop     dword ptr [rax+rax+00h]
0x1800302ad  mov     rcx, [rbx+8]
0x1800302b1  mov     [rcx], eax
0x1800302b3  mov     rax, [rbx+8]
0x1800302b7  cmp     dword ptr [rax], 0
0x1800302ba  jl      loc_180030348
0x1800302c0  mov     rcx, [rbx]; this
0x1800302c3  call    ?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)
0x1800302c8  mov     rcx, [rbx+8]
0x1800302cc  mov     [rcx], eax
0x1800302ce  mov     rax, [rbx+8]
0x1800302d2  mov     r9d, [rax]
0x1800302d5  test    r9d, r9d
0x1800302d8  js      loc_1800303C7
0x1800302de  mov     rax, [rbx]
0x1800302e1  mov     dl, 1
0x1800302e3  mov     [rax+90h], dl
0x1800302e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800302f0  lea     rax, WPP_GLOBAL_Control
0x1800302f7  cmp     rcx, rax
0x1800302fa  jz      short loc_180030302
0x1800302fc  cmp     byte ptr [rcx+19h], 4
0x180030300  jnb     short loc_180030304
0x180030302  xor     dl, dl
0x180030304  lea     rax, WPP_RECORDER_INITIALIZED
0x18003030b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180030312  setnz   r8b
0x180030316  test    dl, dl
0x180030318  jnz     short loc_18003031F
0x18003031a  test    r8b, r8b
0x18003031d  jz      short loc_18003033F
0x18003031f  mov     r9, [rcx+28h]
0x180030323  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18003032a  mov     rcx, [rcx+10h]
0x18003032e  mov     [rsp+58h+var_20], rax
0x180030333  mov     [rsp+58h+var_28], 53h ; 'S'
0x18003033a  call    WPP_RECORDER_AND_TRACE_SF_s
0x18003033f  xor     eax, eax
0x180030341  add     rsp, 50h
0x180030345  pop     rbx
0x180030346  retn
0x180030348  mov     rcx, cs:WPP_GLOBAL_Control
0x18003034f  lea     rax, WPP_GLOBAL_Control
0x180030356  cmp     rcx, rax
0x180030359  jz      short loc_180030365
0x18003035b  cmp     byte ptr [rcx+19h], 2
0x18003035f  jb      short loc_180030365
0x180030361  mov     dl, 1
0x180030363  jmp     short loc_180030367
0x180030365  xor     dl, dl
0x180030367  lea     rax, WPP_RECORDER_INITIALIZED
0x18003036e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180030375  setnz   r8b
0x180030379  test    dl, dl
0x18003037b  jnz     short loc_180030382
0x18003037d  test    r8b, r8b
0x180030380  jz      short loc_1800303A2
0x180030382  mov     r9, [rcx+28h]
0x180030386  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18003038d  mov     rcx, [rcx+10h]
0x180030391  mov     [rsp+58h+var_20], rax
0x180030396  mov     [rsp+58h+var_28], 51h ; 'Q'
0x18003039d  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800303a2  mov     rcx, [rbx+8]
0x1800303a6  mov     ecx, [rcx]
0x1800303a8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800303ad  mov     rcx, [rsp+58h]; this
0x1800303b2  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x1800303b9  mov     r9d, eax; char *
0x1800303bc  mov     edx, 2E5h; void *
0x1800303c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800303c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303ce  lea     rax, WPP_GLOBAL_Control
0x1800303d5  cmp     rcx, rax
0x1800303d8  jz      short loc_1800303E4
0x1800303da  cmp     byte ptr [rcx+19h], 2
0x1800303de  jb      short loc_1800303E4
0x1800303e0  mov     dl, 1
0x1800303e2  jmp     short loc_1800303E6
0x1800303e4  xor     dl, dl
0x1800303e6  lea     rax, WPP_RECORDER_INITIALIZED
0x1800303ed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800303f4  setnz   r8b
0x1800303f8  test    dl, dl
0x1800303fa  jnz     short loc_180030401
0x1800303fc  test    r8b, r8b
0x1800303ff  jz      short loc_180030426
0x180030401  mov     [rsp+58h+var_10], r9d
0x180030406  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18003040d  mov     r9, [rcx+28h]
0x180030411  mov     rcx, [rcx+10h]
0x180030415  mov     [rsp+58h+var_20], rax
0x18003041a  mov     [rsp+58h+var_28], 52h ; 'R'
0x180030421  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180030426  mov     rcx, [rbx+8]
0x18003042a  mov     ecx, [rcx]
0x18003042c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180030431  mov     rcx, [rsp+58h]; this
0x180030436  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18003043d  mov     r9d, eax; char *
0x180030440  mov     edx, 2ECh; void *
0x180030445  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
