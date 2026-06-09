# TlmWriteDehydrationQueued

- ea: `0x1400160dc`
- end: `0x140016425`
- name: `TlmWriteDehydrationQueued`
- size: `841`
- prototype: `__int64 __fastcall(int, int, int, int, PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140047b30`

## callees

- `0x140001008`
- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x1400160dc`
- `0x14001751c`
- `0x140017578`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140016127`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140016127`
- `FLTMGR!FltGetFileNameInformation` at `0x140016152`
- `FLTMGR!FltGetFileNameInformation` at `0x140016152`
- `FLTMGR!FltParseFileNameInformation` at `0x140016170`
- `FLTMGR!FltParseFileNameInformation` at `0x140016170`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400163f8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400163f8`

## pseudocode

```c
void __fastcall TlmWriteDehydrationQueued(__int64 a1, __int64 a2, __int64 a3, int a4, PFLT_CALLBACK_DATA CallbackData)
{
  int v7; // r14d
  __int64 *v8; // rbx
  signed __int64 UnbiasedInterruptTime; // rsi
  NTSTATUS v10; // eax
  int v11; // edx
  NTSTATUS v12; // r15d
  UNICODE_STRING *p_FinalComponent; // rbx
  UNICODE_STRING *p_Extension; // rdi
  int v15; // eax
  int v16; // r11d
  __int64 v17; // r10
  __int64 v18; // r8
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  __int64 *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  __int64 *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  __int64 *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  __int64 *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]

  v19 = a3;
  v20 = a2;
  if ( _TLM )
  {
    v7 = 0;
    FileNameInformation = 0;
    v8 = &TlmMsgNoFileExtension;
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v10 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
    v11 = 15;
    v12 = v10;
    if ( !v10 )
    {
      if ( FltParseFileNameInformation(FileNameInformation) < 0 )
      {
        v11 = 15;
      }
      else
      {
        p_FinalComponent = &FileNameInformation->FinalComponent;
        p_Extension = &FileNameInformation->Extension;
        TlmiSearchForOneDriveInvalidFilenames(&FileNameInformation->FinalComponent);
        v15 = TlmiSearchForOneDriveInvalidChars(p_FinalComponent);
        v11 = v12 + 15;
        v7 = v16 | v15;
        v8 = (__int64 *)TlmMsgLongFileExtension;
        if ( p_Extension->Length <= (unsigned __int16)(v12 + 15) )
          v8 = (__int64 *)p_Extension;
      }
    }
    if ( UnbiasedInterruptTime > qword_1400295E8 )
    {
      dword_1400295E0 = 0;
      qword_1400295E8 = UnbiasedInterruptTime + 36000000000LL;
    }
    if ( a1 && dword_1400295E0 < v11 )
    {
      ++dword_1400295E0;
      if ( **(_DWORD **)&qword_1400295A8 > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
      {
        tlgCreate1Sz_char(v26, a1 + 1);
        v27 = &v22;
        v23 = v19;
        v22 = v20;
        v29 = &v23;
        v28 = 8;
        v31 = &v20;
        v33 = &v36;
        v35 = (__int64 *)v8[1];
        v36 = *(unsigned __int16 *)v8;
        v37 = &v19;
        v39 = &v24;
        v30 = 8;
        LODWORD(v20) = a4;
        v32 = 4;
        v34 = 2;
        LODWORD(v19) = v7;
        v38 = 4;
        v24 = 0x1000000;
        v40 = 8;
        tlgWriteTransfer_EtwWriteTransfer(v17, (unsigned __int8 *)byte_140022E29, 0, 0, 0xAu, &v25);
      }
    }
    else if ( **(_DWORD **)&qword_1400295A8 > 5u
           && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
    {
      v24 = 1;
      v26[0] = &v24;
      v23 = v19;
      v26[1] = 8;
      v27 = &v23;
      v29 = &v19;
      v31 = &v34;
      v33 = (__int64 *)v8[1];
      v34 = *(unsigned __int16 *)v8;
      v35 = &v20;
      v37 = &v22;
      v28 = 8;
      LODWORD(v19) = a4;
      v30 = 4;
      v32 = 2;
      LODWORD(v20) = v7;
      v36 = 4;
      v22 = 0x1000000;
      v38 = 8;
      tlgWriteAgg(v18, (unsigned __int8 *)&byte_140022419, v18, 9u, &v25);
    }
    if ( !v12 )
      FltReleaseFileNameInformation(FileNameInformation);
  }
}

```

## disassembly

```asm
0x1400160dc  push    rbp
0x1400160de  push    rbx
0x1400160df  push    rsi
0x1400160e0  push    rdi
0x1400160e1  push    r12
0x1400160e3  push    r13
0x1400160e5  push    r14
0x1400160e7  push    r15
0x1400160e9  lea     rbp, [rsp-18h]
0x1400160ee  sub     rsp, 118h
0x1400160f5  mov     rax, cs:__security_cookie
0x1400160fc  xor     rax, rsp
0x1400160ff  mov     [rbp+50h+var_50], rax
0x140016103  cmp     cs:__TLM, 0
0x14001610a  mov     r12d, r9d
0x14001610d  mov     rdi, [rbp+50h+CallbackData]
0x140016114  mov     r13, rcx
0x140016117  mov     [rsp+150h+var_120], r8
0x14001611c  mov     [rsp+150h+var_118], rdx
0x140016121  jz      loc_140016404
0x140016127  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14001612e  nop     dword ptr [rax+rax+00h]
0x140016133  xor     r14d, r14d
0x140016136  lea     r8, [rsp+150h+FileNameInformation]; FileNameInformation
0x14001613b  mov     edx, 101h; NameOptions
0x140016140  mov     [rsp+150h+FileNameInformation], r14
0x140016145  mov     rcx, rdi; CallbackData
0x140016148  lea     rbx, TlmMsgNoFileExtension
0x14001614f  mov     rsi, rax
0x140016152  call    cs:__imp_FltGetFileNameInformation
0x140016159  nop     dword ptr [rax+rax+00h]
0x14001615e  xor     edi, edi
0x140016160  lea     edx, [r14+0Fh]
0x140016164  mov     r15d, eax
0x140016167  test    eax, eax
0x140016169  jnz     short loc_1400161C1
0x14001616b  mov     rcx, [rsp+150h+FileNameInformation]; FileNameInformation
0x140016170  call    cs:__imp_FltParseFileNameInformation
0x140016177  nop     dword ptr [rax+rax+00h]
0x14001617c  test    eax, eax
0x14001617e  js      short loc_1400161BC
0x140016180  mov     rcx, [rsp+150h+FileNameInformation]
0x140016185  lea     rbx, [rcx+58h]
0x140016189  lea     rdi, [rcx+38h]
0x14001618d  mov     rcx, rbx
0x140016190  call    TlmiSearchForOneDriveInvalidFilenames
0x140016195  mov     rcx, rbx
0x140016198  mov     r11d, eax
0x14001619b  call    TlmiSearchForOneDriveInvalidChars
0x1400161a0  mov     r14d, eax
0x1400161a3  lea     edx, [r15+0Fh]
0x1400161a7  or      r14d, r11d
0x1400161aa  lea     rbx, TlmMsgLongFileExtension; "\"$"
0x1400161b1  cmp     [rdi], dx
0x1400161b4  cmovbe  rbx, rdi
0x1400161b8  xor     edi, edi
0x1400161ba  jmp     short loc_1400161C1
0x1400161bc  mov     edx, 0Fh
0x1400161c1  cmp     rsi, cs:qword_1400295E8
0x1400161c8  jle     short loc_1400161E4
0x1400161ca  mov     rcx, 861C46800h
0x1400161d4  mov     cs:dword_1400295E0, edi
0x1400161da  add     rcx, rsi
0x1400161dd  mov     cs:qword_1400295E8, rcx
0x1400161e4  test    r13, r13
0x1400161e7  jz      loc_140016306
0x1400161ed  mov     eax, cs:dword_1400295E0
0x1400161f3  cmp     eax, edx
0x1400161f5  jge     loc_140016306
0x1400161fb  mov     r10, cs:qword_1400295A8
0x140016202  inc     eax
0x140016204  mov     cs:dword_1400295E0, eax
0x14001620a  mov     eax, [r10]
0x14001620d  cmp     eax, 5
0x140016210  jbe     loc_1400163EE
0x140016216  mov     rdx, 400000000000h
0x140016220  mov     rcx, r10
0x140016223  call    _tlgKeywordOn
0x140016228  test    al, al
0x14001622a  jz      loc_1400163EE
0x140016230  lea     rdx, [r13+1]
0x140016234  lea     rcx, [rbp+50h+var_D0]
0x140016238  call    _tlgCreate1Sz_char
0x14001623d  mov     rcx, [rsp+150h+var_118]
0x140016242  lea     rax, [rsp+150h+var_108]
0x140016247  mov     [rbp+50h+var_C0], rax
0x14001624b  lea     rdx, byte_140022E29
0x140016252  mov     rax, [rsp+150h+var_120]
0x140016257  xor     r9d, r9d
0x14001625a  mov     [rsp+150h+var_100], rax
0x14001625f  xor     r8d, r8d
0x140016262  lea     rax, [rsp+150h+var_100]
0x140016267  mov     [rsp+150h+var_108], rcx
0x14001626c  mov     [rbp+50h+var_B0], rax
0x140016270  mov     rcx, r10
0x140016273  lea     rax, [rsp+150h+var_118]
0x140016278  mov     [rbp+50h+var_B8], 8
0x140016280  mov     [rbp+50h+var_A0], rax
0x140016284  lea     rax, [rbp+50h+var_78]
0x140016288  mov     [rbp+50h+var_90], rax
0x14001628c  mov     rax, [rbx+8]
0x140016290  mov     [rbp+50h+var_80], rax
0x140016294  movzx   eax, word ptr [rbx]
0x140016297  mov     dword ptr [rbp+50h+var_78], eax
0x14001629a  lea     rax, [rsp+150h+var_120]
0x14001629f  mov     [rbp+50h+var_70], rax
0x1400162a3  lea     rax, [rsp+150h+var_F8]
0x1400162a8  mov     [rbp+50h+var_60], rax
0x1400162ac  lea     rax, [rsp+150h+var_F0]
0x1400162b1  mov     [rsp+150h+var_128], rax
0x1400162b6  mov     dword ptr [rsp+150h+var_130], 0Ah
0x1400162be  mov     [rbp+50h+var_A8], 8
0x1400162c6  mov     dword ptr [rsp+150h+var_118], r12d
0x1400162cb  mov     [rbp+50h+var_98], 4
0x1400162d3  mov     [rbp+50h+var_88], 2
0x1400162db  mov     dword ptr [rbp+50h+var_78+4], edi
0x1400162de  mov     dword ptr [rsp+150h+var_120], r14d
0x1400162e3  mov     [rbp+50h+var_68], 4
0x1400162eb  mov     [rsp+150h+var_F8], 1000000h
0x1400162f4  mov     [rbp+50h+var_58], 8
0x1400162fc  call    _tlgWriteTransfer_EtwWriteTransfer
0x140016301  jmp     loc_1400163EE
0x140016306  mov     r8, cs:qword_1400295A8
0x14001630d  mov     eax, [r8]
0x140016310  cmp     eax, 5
0x140016313  jbe     loc_1400163EE
0x140016319  mov     rdx, 400000000000h
0x140016323  mov     rcx, r8
0x140016326  call    _tlgKeywordOn
0x14001632b  test    al, al
0x14001632d  jz      loc_1400163EE
0x140016333  lea     rax, [rsp+150h+var_F8]
0x140016338  mov     [rsp+150h+var_F8], 1
0x140016341  mov     [rbp+50h+var_D0], rax
0x140016345  lea     rdx, byte_140022419; int
0x14001634c  mov     rax, [rsp+150h+var_120]
0x140016351  mov     r9d, 9; int
0x140016357  mov     [rsp+150h+var_100], rax
0x14001635c  mov     rcx, r8; int
0x14001635f  lea     rax, [rsp+150h+var_100]
0x140016364  mov     [rbp+50h+var_C8], 8
0x14001636c  mov     [rbp+50h+var_C0], rax
0x140016370  lea     rax, [rsp+150h+var_120]
0x140016375  mov     [rbp+50h+var_B0], rax
0x140016379  lea     rax, [rbp+50h+var_88]
0x14001637d  mov     [rbp+50h+var_A0], rax
0x140016381  mov     rax, [rbx+8]
0x140016385  mov     [rbp+50h+var_90], rax
0x140016389  movzx   eax, word ptr [rbx]
0x14001638c  mov     dword ptr [rbp+50h+var_88], eax
0x14001638f  lea     rax, [rsp+150h+var_118]
0x140016394  mov     [rbp+50h+var_80], rax
0x140016398  lea     rax, [rsp+150h+var_108]
0x14001639d  mov     [rbp+50h+var_70], rax
0x1400163a1  lea     rax, [rsp+150h+var_F0]
0x1400163a6  mov     [rsp+150h+var_130], rax; PEVENT_DATA_DESCRIPTOR
0x1400163ab  mov     [rbp+50h+var_B8], 8
0x1400163b3  mov     dword ptr [rsp+150h+var_120], r12d
0x1400163b8  mov     [rbp+50h+var_A8], 4
0x1400163c0  mov     [rbp+50h+var_98], 2
0x1400163c8  mov     dword ptr [rbp+50h+var_88+4], edi
0x1400163cb  mov     dword ptr [rsp+150h+var_118], r14d
0x1400163d0  mov     [rbp+50h+var_78], 4
0x1400163d8  mov     [rsp+150h+var_108], 1000000h
0x1400163e1  mov     [rbp+50h+var_68], 8
0x1400163e9  call    _tlgWriteAgg
0x1400163ee  test    r15d, r15d
0x1400163f1  jnz     short loc_140016404
0x1400163f3  mov     rcx, [rsp+150h+FileNameInformation]; FileNameInformation
0x1400163f8  call    cs:__imp_FltReleaseFileNameInformation
0x1400163ff  nop     dword ptr [rax+rax+00h]
0x140016404  mov     rcx, [rbp+50h+var_50]
0x140016408  xor     rcx, rsp; StackCookie
0x14001640b  call    __security_check_cookie
0x140016410  add     rsp, 118h
0x140016417  pop     r15
0x140016419  pop     r14
0x14001641b  pop     r13
0x14001641d  pop     r12
0x14001641f  pop     rdi
0x140016420  pop     rsi
0x140016421  pop     rbx
0x140016422  pop     rbp
0x140016423  retn
```
