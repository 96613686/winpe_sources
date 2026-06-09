# wil::details::functor_wrapper_void__lambda_93208eb893f380cc48155d176decd6a1___::Run

- ea: `0x1800300a0`
- end: `0x180030262`
- name: `wil::details::functor_wrapper_void__lambda_93208eb893f380cc48155d176decd6a1___::Run`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002dd44`

## callees

- `0x180003740`
- `0x180011b9c`
- `0x180012004`
- `0x1800120b8`
- `0x1800300a0`

## import_xrefs

- `deviceassociation!DafSelectCeremony` at `0x1800300bc`
- `deviceassociation!DafSelectCeremony` at `0x1800300bc`

## string_xrefs

- `0x18003024d`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_93208eb893f380cc48155d176decd6a1___::Run(__int64 a1)
{
  int **v1; // rbx
  int v2; // edx
  int v3; // r8d
  unsigned int *v4; // rcx
  bool v5; // dl
  bool v6; // dl
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(int ***)(a1 + 8);
  **v1 = DafSelectCeremony(*((_QWORD *)v1[1] + 255), v1[1] + 40);
  if ( **v1 < 0 )
  {
    LOBYTE(v2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v8 = wil::verify_hresult<long>((unsigned int)**v1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v8,
      v9);
  }
  *(_OWORD *)(v1[1] + 90) = *((_OWORD *)v1[1] + 10);
  v4 = (unsigned int *)v1[1];
  if ( DAF_Ceremony_JustWorks == *((_QWORD *)v4 + 20) && *((_QWORD *)v4 + 21) == 0x4B4D953B27A55DB2LL )
  {
    v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  else
  {
    v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    **v1 = -2147418113;
  }
  return 0;
}

```

## disassembly

```asm
0x1800300a0  push    rbx
0x1800300a2  sub     rsp, 50h
0x1800300a6  mov     rbx, [rcx+8]
0x1800300aa  mov     rdx, [rbx+8]
0x1800300ae  mov     rcx, [rdx+7F8h]
0x1800300b5  add     rdx, 0A0h
0x1800300bc  call    cs:__imp_DafSelectCeremony
0x1800300c3  nop     dword ptr [rax+rax+00h]
0x1800300c8  mov     rcx, [rbx]
0x1800300cb  mov     [rcx], eax
0x1800300cd  mov     rax, [rbx]
0x1800300d0  mov     r9d, [rax]
0x1800300d3  test    r9d, r9d
0x1800300d6  js      loc_1800301DF
0x1800300dc  mov     rax, [rbx+8]
0x1800300e0  movups  xmm0, xmmword ptr [rax+0A0h]
0x1800300e7  movdqu  xmmword ptr [rax+168h], xmm0
0x1800300ef  mov     rcx, [rbx+8]
0x1800300f3  mov     rax, cs:DAF_Ceremony_JustWorks
0x1800300fa  cmp     rax, [rcx+0A0h]
0x180030101  jnz     short loc_180030173
0x180030103  mov     rax, cs:qword_18003E1B8
0x18003010a  cmp     rax, [rcx+0A8h]
0x180030111  jnz     short loc_180030173
0x180030113  mov     rcx, cs:WPP_GLOBAL_Control
0x18003011a  lea     rax, WPP_GLOBAL_Control
0x180030121  cmp     rcx, rax
0x180030124  jz      short loc_180030130
0x180030126  cmp     byte ptr [rcx+19h], 4
0x18003012a  jb      short loc_180030130
0x18003012c  mov     dl, 1
0x18003012e  jmp     short loc_180030132
0x180030130  xor     dl, dl
0x180030132  lea     rax, WPP_RECORDER_INITIALIZED
0x180030139  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180030140  setnz   r8b
0x180030144  test    dl, dl
0x180030146  jnz     short loc_180030151
0x180030148  test    r8b, r8b
0x18003014b  jz      loc_1800301D6
0x180030151  mov     r9, [rcx+28h]
0x180030155  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18003015c  mov     rcx, [rcx+10h]
0x180030160  mov     [rsp+58h+var_20], rax
0x180030165  mov     [rsp+58h+var_28], 4Dh ; 'M'
0x18003016c  call    WPP_RECORDER_AND_TRACE_SF_s
0x180030171  jmp     short loc_1800301D6
0x180030173  mov     rcx, cs:WPP_GLOBAL_Control
0x18003017a  lea     rax, WPP_GLOBAL_Control
0x180030181  cmp     rcx, rax
0x180030184  jz      short loc_180030190
0x180030186  cmp     byte ptr [rcx+19h], 2
0x18003018a  jb      short loc_180030190
0x18003018c  mov     dl, 1
0x18003018e  jmp     short loc_180030192
0x180030190  xor     dl, dl
0x180030192  lea     rax, WPP_RECORDER_INITIALIZED
0x180030199  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800301a0  setnz   r8b
0x1800301a4  test    dl, dl
0x1800301a6  jnz     short loc_1800301AD
0x1800301a8  test    r8b, r8b
0x1800301ab  jz      short loc_1800301CD
0x1800301ad  mov     r9, [rcx+28h]
0x1800301b1  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x1800301b8  mov     rcx, [rcx+10h]
0x1800301bc  mov     [rsp+58h+var_20], rax
0x1800301c1  mov     [rsp+58h+var_28], 4Eh ; 'N'
0x1800301c8  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800301cd  mov     rax, [rbx]
0x1800301d0  mov     dword ptr [rax], 8000FFFFh
0x1800301d6  xor     eax, eax
0x1800301d8  add     rsp, 50h
0x1800301dc  pop     rbx
0x1800301dd  retn
0x1800301df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800301e6  lea     rax, WPP_GLOBAL_Control
0x1800301ed  cmp     rcx, rax
0x1800301f0  jz      short loc_1800301FC
0x1800301f2  cmp     byte ptr [rcx+19h], 2
0x1800301f6  jb      short loc_1800301FC
0x1800301f8  mov     dl, 1
0x1800301fa  jmp     short loc_1800301FE
0x1800301fc  xor     dl, dl
0x1800301fe  lea     rax, WPP_RECORDER_INITIALIZED
0x180030205  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003020c  setnz   r8b
0x180030210  test    dl, dl
0x180030212  jnz     short loc_180030219
0x180030214  test    r8b, r8b
0x180030217  jz      short loc_18003023E
0x180030219  mov     [rsp+58h+var_10], r9d
0x18003021e  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180030225  mov     r9, [rcx+28h]
0x180030229  mov     rcx, [rcx+10h]
0x18003022d  mov     [rsp+58h+var_20], rax
0x180030232  mov     [rsp+58h+var_28], 4Ch ; 'L'
0x180030239  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18003023e  mov     rcx, [rbx]
0x180030241  mov     ecx, [rcx]
0x180030243  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180030248  mov     rcx, [rsp+58h]; this
0x18003024d  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x180030254  mov     r9d, eax; char *
0x180030257  mov     edx, 2BDh; void *
0x18003025c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
