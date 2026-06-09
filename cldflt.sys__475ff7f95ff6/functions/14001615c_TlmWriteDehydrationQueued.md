# TlmWriteDehydrationQueued

- ea: `0x14001615c`
- end: `0x1400164a5`
- name: `TlmWriteDehydrationQueued`
- size: `841`
- prototype: `__int64 __fastcall(int, int, int, int, PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140047c20`

## callees

- `0x140001008`
- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x14001615c`
- `0x14001759c`
- `0x1400175f8`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400161a7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400161a7`
- `FLTMGR!FltGetFileNameInformation` at `0x1400161d2`
- `FLTMGR!FltGetFileNameInformation` at `0x1400161d2`
- `FLTMGR!FltParseFileNameInformation` at `0x1400161f0`
- `FLTMGR!FltParseFileNameInformation` at `0x1400161f0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140016478`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140016478`

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
      if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
      {
        tlgCreate1Sz_char((__int64)v26, (__int16 *)(a1 + 1));
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
        tlgWriteTransfer_EtwWriteTransfer(v17, (unsigned __int8 *)&word_140022F86, 0, 0, 0xAu, &v25);
      }
    }
    else if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
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
0x14001615c  push    rbp
0x14001615e  push    rbx
0x14001615f  push    rsi
0x140016160  push    rdi
0x140016161  push    r12
0x140016163  push    r13
0x140016165  push    r14
0x140016167  push    r15
0x140016169  lea     rbp, [rsp-18h]
0x14001616e  sub     rsp, 118h
0x140016175  mov     rax, cs:__security_cookie
0x14001617c  xor     rax, rsp
0x14001617f  mov     [rbp+50h+var_50], rax
0x140016183  cmp     cs:__TLM, 0
0x14001618a  mov     r12d, r9d
0x14001618d  mov     rdi, [rbp+50h+CallbackData]
0x140016194  mov     r13, rcx
0x140016197  mov     [rsp+150h+var_120], r8
0x14001619c  mov     [rsp+150h+var_118], rdx
0x1400161a1  jz      loc_140016484
0x1400161a7  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400161ae  nop     dword ptr [rax+rax+00h]
0x1400161b3  xor     r14d, r14d
0x1400161b6  lea     r8, [rsp+150h+FileNameInformation]; FileNameInformation
0x1400161bb  mov     edx, 101h; NameOptions
0x1400161c0  mov     [rsp+150h+FileNameInformation], r14
0x1400161c5  mov     rcx, rdi; CallbackData
0x1400161c8  lea     rbx, TlmMsgNoFileExtension
0x1400161cf  mov     rsi, rax
0x1400161d2  call    cs:__imp_FltGetFileNameInformation
0x1400161d9  nop     dword ptr [rax+rax+00h]
0x1400161de  xor     edi, edi
0x1400161e0  lea     edx, [r14+0Fh]
0x1400161e4  mov     r15d, eax
0x1400161e7  test    eax, eax
0x1400161e9  jnz     short loc_140016241
0x1400161eb  mov     rcx, [rsp+150h+FileNameInformation]; FileNameInformation
0x1400161f0  call    cs:__imp_FltParseFileNameInformation
0x1400161f7  nop     dword ptr [rax+rax+00h]
0x1400161fc  test    eax, eax
0x1400161fe  js      short loc_14001623C
0x140016200  mov     rcx, [rsp+150h+FileNameInformation]
0x140016205  lea     rbx, [rcx+58h]
0x140016209  lea     rdi, [rcx+38h]
0x14001620d  mov     rcx, rbx
0x140016210  call    TlmiSearchForOneDriveInvalidFilenames
0x140016215  mov     rcx, rbx
0x140016218  mov     r11d, eax
0x14001621b  call    TlmiSearchForOneDriveInvalidChars
0x140016220  mov     r14d, eax
0x140016223  lea     edx, [r15+0Fh]
0x140016227  or      r14d, r11d
0x14001622a  lea     rbx, TlmMsgLongFileExtension; "\"$"
0x140016231  cmp     [rdi], dx
0x140016234  cmovbe  rbx, rdi
0x140016238  xor     edi, edi
0x14001623a  jmp     short loc_140016241
0x14001623c  mov     edx, 0Fh
0x140016241  cmp     rsi, cs:qword_1400295E8
0x140016248  jle     short loc_140016264
0x14001624a  mov     rcx, 861C46800h
0x140016254  mov     cs:dword_1400295E0, edi
0x14001625a  add     rcx, rsi
0x14001625d  mov     cs:qword_1400295E8, rcx
0x140016264  test    r13, r13
0x140016267  jz      loc_140016386
0x14001626d  mov     eax, cs:dword_1400295E0
0x140016273  cmp     eax, edx
0x140016275  jge     loc_140016386
0x14001627b  mov     r10, cs:qword_1400295A8
0x140016282  inc     eax
0x140016284  mov     cs:dword_1400295E0, eax
0x14001628a  mov     eax, [r10]
0x14001628d  cmp     eax, 5
0x140016290  jbe     loc_14001646E
0x140016296  mov     rdx, 400000000000h
0x1400162a0  mov     rcx, r10
0x1400162a3  call    _tlgKeywordOn
0x1400162a8  test    al, al
0x1400162aa  jz      loc_14001646E
0x1400162b0  lea     rdx, [r13+1]
0x1400162b4  lea     rcx, [rbp+50h+var_D0]
0x1400162b8  call    _tlgCreate1Sz_char
0x1400162bd  mov     rcx, [rsp+150h+var_118]
0x1400162c2  lea     rax, [rsp+150h+var_108]
0x1400162c7  mov     [rbp+50h+var_C0], rax
0x1400162cb  lea     rdx, word_140022F86
0x1400162d2  mov     rax, [rsp+150h+var_120]
0x1400162d7  xor     r9d, r9d
0x1400162da  mov     [rsp+150h+var_100], rax
0x1400162df  xor     r8d, r8d
0x1400162e2  lea     rax, [rsp+150h+var_100]
0x1400162e7  mov     [rsp+150h+var_108], rcx
0x1400162ec  mov     [rbp+50h+var_B0], rax
0x1400162f0  mov     rcx, r10
0x1400162f3  lea     rax, [rsp+150h+var_118]
0x1400162f8  mov     [rbp+50h+var_B8], 8
0x140016300  mov     [rbp+50h+var_A0], rax
0x140016304  lea     rax, [rbp+50h+var_78]
0x140016308  mov     [rbp+50h+var_90], rax
0x14001630c  mov     rax, [rbx+8]
0x140016310  mov     [rbp+50h+var_80], rax
0x140016314  movzx   eax, word ptr [rbx]
0x140016317  mov     dword ptr [rbp+50h+var_78], eax
0x14001631a  lea     rax, [rsp+150h+var_120]
0x14001631f  mov     [rbp+50h+var_70], rax
0x140016323  lea     rax, [rsp+150h+var_F8]
0x140016328  mov     [rbp+50h+var_60], rax
0x14001632c  lea     rax, [rsp+150h+var_F0]
0x140016331  mov     [rsp+150h+var_128], rax
0x140016336  mov     dword ptr [rsp+150h+var_130], 0Ah
0x14001633e  mov     [rbp+50h+var_A8], 8
0x140016346  mov     dword ptr [rsp+150h+var_118], r12d
0x14001634b  mov     [rbp+50h+var_98], 4
0x140016353  mov     [rbp+50h+var_88], 2
0x14001635b  mov     dword ptr [rbp+50h+var_78+4], edi
0x14001635e  mov     dword ptr [rsp+150h+var_120], r14d
0x140016363  mov     [rbp+50h+var_68], 4
0x14001636b  mov     [rsp+150h+var_F8], 1000000h
0x140016374  mov     [rbp+50h+var_58], 8
0x14001637c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140016381  jmp     loc_14001646E
0x140016386  mov     r8, cs:qword_1400295A8
0x14001638d  mov     eax, [r8]
0x140016390  cmp     eax, 5
0x140016393  jbe     loc_14001646E
0x140016399  mov     rdx, 400000000000h
0x1400163a3  mov     rcx, r8
0x1400163a6  call    _tlgKeywordOn
0x1400163ab  test    al, al
0x1400163ad  jz      loc_14001646E
0x1400163b3  lea     rax, [rsp+150h+var_F8]
0x1400163b8  mov     [rsp+150h+var_F8], 1
0x1400163c1  mov     [rbp+50h+var_D0], rax
0x1400163c5  lea     rdx, byte_140022419; int
0x1400163cc  mov     rax, [rsp+150h+var_120]
0x1400163d1  mov     r9d, 9; int
0x1400163d7  mov     [rsp+150h+var_100], rax
0x1400163dc  mov     rcx, r8; int
0x1400163df  lea     rax, [rsp+150h+var_100]
0x1400163e4  mov     [rbp+50h+var_C8], 8
0x1400163ec  mov     [rbp+50h+var_C0], rax
0x1400163f0  lea     rax, [rsp+150h+var_120]
0x1400163f5  mov     [rbp+50h+var_B0], rax
0x1400163f9  lea     rax, [rbp+50h+var_88]
0x1400163fd  mov     [rbp+50h+var_A0], rax
0x140016401  mov     rax, [rbx+8]
0x140016405  mov     [rbp+50h+var_90], rax
0x140016409  movzx   eax, word ptr [rbx]
0x14001640c  mov     dword ptr [rbp+50h+var_88], eax
0x14001640f  lea     rax, [rsp+150h+var_118]
0x140016414  mov     [rbp+50h+var_80], rax
0x140016418  lea     rax, [rsp+150h+var_108]
0x14001641d  mov     [rbp+50h+var_70], rax
0x140016421  lea     rax, [rsp+150h+var_F0]
0x140016426  mov     [rsp+150h+var_130], rax; PEVENT_DATA_DESCRIPTOR
0x14001642b  mov     [rbp+50h+var_B8], 8
0x140016433  mov     dword ptr [rsp+150h+var_120], r12d
0x140016438  mov     [rbp+50h+var_A8], 4
0x140016440  mov     [rbp+50h+var_98], 2
0x140016448  mov     dword ptr [rbp+50h+var_88+4], edi
0x14001644b  mov     dword ptr [rsp+150h+var_118], r14d
0x140016450  mov     [rbp+50h+var_78], 4
0x140016458  mov     [rsp+150h+var_108], 1000000h
0x140016461  mov     [rbp+50h+var_68], 8
0x140016469  call    _tlgWriteAgg
0x14001646e  test    r15d, r15d
0x140016471  jnz     short loc_140016484
0x140016473  mov     rcx, [rsp+150h+FileNameInformation]; FileNameInformation
0x140016478  call    cs:__imp_FltReleaseFileNameInformation
0x14001647f  nop     dword ptr [rax+rax+00h]
0x140016484  mov     rcx, [rbp+50h+var_50]
0x140016488  xor     rcx, rsp; StackCookie
0x14001648b  call    __security_check_cookie
0x140016490  add     rsp, 118h
0x140016497  pop     r15
0x140016499  pop     r14
0x14001649b  pop     r13
0x14001649d  pop     r12
0x14001649f  pop     rdi
0x1400164a0  pop     rsi
0x1400164a1  pop     rbx
0x1400164a2  pop     rbp
0x1400164a3  retn
```
