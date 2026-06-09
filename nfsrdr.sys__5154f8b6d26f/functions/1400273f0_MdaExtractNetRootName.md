# MdaExtractNetRootName

- ea: `0x1400273f0`
- end: `0x140027ae6`
- name: `MdaExtractNetRootName`
- size: `1782`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009380`
- `0x1400159cc`
- `0x140015a40`
- `0x140015f84`
- `0x140019d7c`
- `0x140019e3c`
- `0x140019fc4`
- `0x140023dd0`
- `0x140024720`
- `0x1400273f0`
- `0x1400280c4`
- `0x14002a5f0`
- `0x140034a90`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140027929`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140027929`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140027949`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140027949`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140027959`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140027959`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140027879`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140027879`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027549`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400276f1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027549`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400276f1`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140027562`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140027562`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002757d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400277b5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002757d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400277b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279f7`
- `ntoskrnl!ExAllocatePool2` at `0x140027830`
- `ntoskrnl!ExAllocatePool2` at `0x140027830`

## pseudocode

```c
void __fastcall MdaExtractNetRootName(__int64 a1, _QWORD *a2, UNICODE_STRING *a3, _OWORD *a4)
{
  __int64 v4; // r13
  __int64 v8; // r12
  WCHAR *v9; // rdx
  __int64 v10; // rsi
  USHORT v11; // r9
  USHORT v12; // r8
  USHORT v13; // r9
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _FAST_MUTEX *v17; // rcx
  PUNICODE_PREFIX_TABLE_ENTRY v18; // rdi
  USHORT *p_Length; // rax
  USHORT Length; // cx
  USHORT v21; // dx
  char v22; // di
  int v23; // r8d
  int v24; // r8d
  char v25; // di
  USHORT v26; // dx
  unsigned int v27; // ecx
  PACCESS_TOKEN PrimaryToken; // rcx
  USHORT v29; // ax
  unsigned int v30; // ecx
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _LUID AuthenticationId; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING SourceString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+80h] [rbp-80h] BYREF
  __int128 v37; // [rsp+90h] [rbp-70h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v39[20]; // [rsp+C0h] [rbp-40h] BYREF
  char v40[16]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v41[24]; // [rsp+120h] [rbp+20h] BYREF
  int v42[4]; // [rsp+180h] [rbp+80h] BYREF
  int v43; // [rsp+190h] [rbp+90h]
  __int64 v44[10]; // [rsp+1A0h] [rbp+A0h] BYREF

  v4 = a2[6];
  *(_QWORD *)&DestinationString.Length = a1;
  v43 = 0;
  *(_OWORD *)v42 = 0;
  v34 = 0;
  v8 = a1;
  *(_OWORD *)v42 = *(_OWORD *)(v4 + 1376);
  v43 = *(_DWORD *)(v4 + 1392);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  v9 = *(WCHAR **)(v8 + 8);
  v10 = a2[4];
  a3->Buffer = v9;
  v11 = *(_WORD *)v8;
  a3->Length = *(_WORD *)v8;
  v12 = *(_WORD *)(v8 + 2);
  a3->MaximumLength = v12;
  a3->Buffer = &v9[(unsigned __int64)*(unsigned __int16 *)a2[8] >> 1];
  v13 = v11 - *(_WORD *)a2[8];
  a3->Length = v13;
  a3->MaximumLength = v12 - *(_WORD *)a2[8];
  *((_QWORD *)&v34 + 1) = 0;
  LODWORD(v34) = 0;
  if ( v13 )
  {
    if ( (int)MdaUpdateMountTree(v4, a2) < 0 )
      goto LABEL_17;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v10 + 216));
    UnicodePrefix = RtlFindUnicodePrefix(*(PUNICODE_PREFIX_TABLE *)(v10 + 232), a3, 0);
    v17 = *(struct _FAST_MUTEX **)(v10 + 216);
    v18 = UnicodePrefix;
    AuthenticationId = (struct _LUID)UnicodePrefix;
    ExReleaseFastMutex(v17);
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          35,
          (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          (_DWORD)a3,
          (__int64)v18->Prefix);
      p_Length = &v18->Prefix->Length;
      Length = a3->Length;
      v21 = *p_Length;
      if ( *p_Length < a3->Length )
      {
        LOWORD(v34) = Length - v21;
        WORD1(v34) = Length - v21;
        *((_QWORD *)&v34 + 1) = (char *)a3->Buffer + v18->Prefix->Length;
        a3->Length = v18->Prefix->Length;
      }
      goto LABEL_17;
    }
    LOBYTE(v31) = 0;
    FirstName = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, a3);
    v22 = 0;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v10 + 216));
    if ( (unsigned __int8)MdaFindPrefixOfUnicodePrefix(
                            *(_QWORD *)(v10 + 232),
                            (int)a3,
                            v23,
                            (int)&AuthenticationId,
                            (__int64)&v31,
                            &FirstName) )
    {
      do
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZdZZ(
            WPP_GLOBAL_Control->AttachedDevice,
            37,
            (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
            *(_QWORD *)(*(_QWORD *)&AuthenticationId + 48LL),
            v31,
            (__int64)&FirstName,
            (__int64)a3);
        v22 = 1;
      }
      while ( (unsigned __int8)MdaFindPrefixOfUnicodePrefix(
                                 *(_QWORD *)(v10 + 232),
                                 (int)a3,
                                 v24,
                                 (int)&AuthenticationId,
                                 (__int64)&v31,
                                 &FirstName) );
      LODWORD(v8) = *(_DWORD *)&DestinationString.Length;
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v10 + 216));
    if ( !v22 )
    {
      DestinationString = 0;
      SourceString = 0;
      v37 = 0;
      memset(v39, 0, 0x4Cu);
      AuthenticationId = 0;
      memset(&SubjectContext, 0, sizeof(SubjectContext));
      memset(v44, 0, 0x44u);
      memset(v41, 0, 0x58u);
      DestinationString.Buffer = (PWSTR)ExAllocatePool2(258, 520, 894592590);
      if ( !DestinationString.Buffer )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
        goto LABEL_17;
      }
      v25 = 1;
      SourceString.MaximumLength = a3->MaximumLength;
      SourceString.Length = a3->Length;
      SourceString.Buffer = a3->Buffer;
      *(_DWORD *)&DestinationString.Length = 34078720;
      while ( 1 )
      {
        RtlCopyUnicodeString(&DestinationString, &SourceString);
        v26 = DestinationString.Length;
        v27 = 0;
        if ( (DestinationString.Length & 0xFFFE) != 0 )
        {
          do
          {
            if ( DestinationString.Buffer[v27] == 92 )
            {
              DestinationString.Buffer[v27] = 47;
              v26 = DestinationString.Length;
            }
            ++v27;
          }
          while ( v27 < v26 >> 1 );
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            38,
            WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
            &DestinationString);
        if ( (unsigned int)MntMount((int)a2, 0, 0, (int)v42, &DestinationString, (__int64)v44) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
          }
        }
        else
        {
          if ( v25 )
          {
            SeCaptureSubjectContext(&SubjectContext);
            PrimaryToken = SubjectContext.PrimaryToken;
            if ( SubjectContext.ClientToken )
              PrimaryToken = SubjectContext.ClientToken;
            SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
            SeReleaseSubjectContext(&SubjectContext);
            if ( (unsigned int)NuiCheckDefault(&AuthenticationId, 1, v39) )
            {
              v39[0] = *(_DWORD *)(v4 + 2332);
              v39[1] = *(_DWORD *)(v4 + 2336);
              v39[2] = 0;
            }
            else
            {
              v25 = 0;
            }
          }
          if ( (unsigned int)NfsGetNonCachedAttributes(a2, v39, v44, v41) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
            }
          }
          else if ( v41[0] == 2 )
          {
            v29 = a3->Length;
            v30 = SourceString.Length;
            if ( SourceString.Length < a3->Length )
            {
              a3->Length = SourceString.Length;
              LOWORD(v34) = v29 - v30;
              WORD1(v34) = v29 - v30;
              *((_QWORD *)&v34 + 1) = (char *)a3->Buffer + v30;
            }
            MntUnmount(a2, &DestinationString);
LABEL_58:
            ExFreePoolWithTag(DestinationString.Buffer, 0);
            break;
          }
          MntUnmount(a2, &DestinationString);
        }
        MdaDissectNameTail(&SourceString, &v37, v40);
        SourceString.Buffer = (PWSTR)*((_QWORD *)&v37 + 1);
        SourceString.Length = v37;
        if ( !(_WORD)v37 )
          goto LABEL_58;
      }
    }
LABEL_17:
    if ( a4 )
      *a4 = v34;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_ZZZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          42,
          (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          v8,
          a2[8],
          (__int64)a3,
          (__int64)&v34);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      {
        v15 = 43;
        goto LABEL_25;
      }
    }
  }
  else
  {
    if ( a4 )
      *a4 = v34;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      v15 = 34;
LABEL_25:
      WPP_SF_(v14->AttachedDevice, v15, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1400273f0  push    rbp
0x1400273f2  push    rbx
0x1400273f3  push    rsi
0x1400273f4  push    rdi
0x1400273f5  push    r12
0x1400273f7  push    r13
0x1400273f9  push    r14
0x1400273fb  push    r15
0x1400273fd  lea     rbp, [rsp-108h]
0x140027405  sub     rsp, 208h
0x14002740c  mov     rax, cs:__security_cookie
0x140027413  xor     rax, rsp
0x140027416  mov     [rbp+140h+var_50], rax
0x14002741d  mov     r13, [rdx+30h]
0x140027421  xorps   xmm0, xmm0
0x140027424  xor     eax, eax
0x140027426  mov     qword ptr [rsp+240h+DestinationString.Length], rcx
0x14002742b  mov     [rbp+140h+var_B0], eax
0x140027431  xorps   xmm1, xmm1
0x140027434  movups  xmmword ptr [rbp+140h+var_C0], xmm1
0x14002743b  mov     r15, r9
0x14002743e  mov     rbx, r8
0x140027441  movups  [rsp+240h+var_1E0], xmm0
0x140027446  mov     r14, rdx
0x140027449  mov     r12, rcx
0x14002744c  movups  xmm0, xmmword ptr [r13+560h]
0x140027454  movups  xmmword ptr [rbp+140h+var_C0], xmm0
0x14002745b  mov     eax, [r13+570h]
0x140027462  mov     [rbp+140h+var_B0], eax
0x140027468  mov     rcx, cs:WPP_GLOBAL_Control
0x14002746f  lea     r10, WPP_GLOBAL_Control
0x140027476  cmp     rcx, r10
0x140027479  jz      short loc_14002749E
0x14002747b  mov     eax, [rcx+2Ch]
0x14002747e  test    al, 8
0x140027480  jz      short loc_14002749E
0x140027482  mov     rcx, [rcx+18h]
0x140027486  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002748d  mov     edx, 21h ; '!'
0x140027492  call    WPP_SF_
0x140027497  lea     r10, WPP_GLOBAL_Control
0x14002749e  mov     rdx, [r12+8]
0x1400274a3  xor     edi, edi
0x1400274a5  mov     rsi, [r14+20h]
0x1400274a9  mov     [rbx+8], rdx
0x1400274ad  movzx   r9d, word ptr [r12]
0x1400274b2  mov     [rbx], r9w
0x1400274b6  movzx   r8d, word ptr [r12+2]
0x1400274bc  mov     [rbx+2], r8w
0x1400274c1  mov     rax, [r14+40h]
0x1400274c5  movzx   ecx, word ptr [rax]
0x1400274c8  shr     rcx, 1
0x1400274cb  lea     rax, [rdx+rcx*2]
0x1400274cf  mov     [rbx+8], rax
0x1400274d3  mov     rax, [r14+40h]
0x1400274d7  sub     r9w, [rax]
0x1400274db  mov     [rbx], r9w
0x1400274df  mov     rax, [r14+40h]
0x1400274e3  sub     r8w, [rax]
0x1400274e7  mov     [rbx+2], r8w
0x1400274ec  mov     qword ptr [rsp+240h+var_1E0+8], rdi
0x1400274f1  mov     dword ptr [rsp+240h+var_1E0], edi
0x1400274f5  test    r9w, r9w
0x1400274f9  jnz     short loc_14002752F
0x1400274fb  test    r15, r15
0x1400274fe  jz      short loc_14002750A
0x140027500  movups  xmm0, [rsp+240h+var_1E0]
0x140027505  movdqu  xmmword ptr [r15], xmm0
0x14002750a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027511  cmp     rcx, r10
0x140027514  jz      loc_140027685
0x14002751a  mov     eax, [rcx+2Ch]
0x14002751d  test    al, 2
0x14002751f  jz      loc_140027685
0x140027525  mov     edx, 22h ; '"'
0x14002752a  jmp     loc_140027675
0x14002752f  mov     rdx, r14
0x140027532  mov     rcx, r13
0x140027535  call    MdaUpdateMountTree
0x14002753a  test    eax, eax
0x14002753c  js      loc_140027604
0x140027542  mov     rcx, [rsi+0D8h]; FastMutex
0x140027549  call    cs:__imp_ExAcquireFastMutex
0x140027550  nop     dword ptr [rax+rax+00h]
0x140027555  mov     rcx, [rsi+0E8h]; PrefixTable
0x14002755c  xor     r8d, r8d; CaseInsensitiveIndex
0x14002755f  mov     rdx, rbx; FullName
0x140027562  call    cs:__imp_RtlFindUnicodePrefix
0x140027569  nop     dword ptr [rax+rax+00h]
0x14002756e  mov     rcx, [rsi+0D8h]; FastMutex
0x140027575  mov     rdi, rax
0x140027578  mov     qword ptr [rsp+240h+AuthenticationId.LowPart], rax
0x14002757d  call    cs:__imp_ExReleaseFastMutex
0x140027584  nop     dword ptr [rax+rax+00h]
0x140027589  test    rdi, rdi
0x14002758c  jz      loc_1400276A9
0x140027592  mov     rcx, cs:WPP_GLOBAL_Control
0x140027599  lea     rax, WPP_GLOBAL_Control
0x1400275a0  cmp     rcx, rax
0x1400275a3  jz      short loc_1400275CE
0x1400275a5  mov     edx, [rcx+2Ch]
0x1400275a8  test    dl, 2
0x1400275ab  jz      short loc_1400275CE
0x1400275ad  mov     rax, [rdi+30h]
0x1400275b1  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400275b8  mov     rcx, [rcx+18h]
0x1400275bc  mov     edx, 23h ; '#'
0x1400275c1  mov     r9, rbx
0x1400275c4  mov     [rsp+240h+var_220], rax
0x1400275c9  call    WPP_SF_ZZ
0x1400275ce  mov     rax, [rdi+30h]
0x1400275d2  movzx   ecx, word ptr [rbx]
0x1400275d5  movzx   edx, word ptr [rax]
0x1400275d8  cmp     dx, cx
0x1400275db  jnb     short loc_140027604
0x1400275dd  sub     cx, dx
0x1400275e0  mov     word ptr [rsp+240h+var_1E0], cx
0x1400275e5  mov     word ptr [rsp+240h+var_1E0+2], cx
0x1400275ea  mov     rax, [rdi+30h]
0x1400275ee  movzx   ecx, word ptr [rax]
0x1400275f1  add     rcx, [rbx+8]
0x1400275f5  mov     qword ptr [rsp+240h+var_1E0+8], rcx
0x1400275fa  mov     rax, [rdi+30h]
0x1400275fe  movzx   ecx, word ptr [rax]
0x140027601  mov     [rbx], cx
0x140027604  lea     rdi, WPP_GLOBAL_Control
0x14002760b  test    r15, r15
0x14002760e  jz      short loc_14002761A
0x140027610  movups  xmm0, [rsp+240h+var_1E0]
0x140027615  movdqu  xmmword ptr [r15], xmm0
0x14002761a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027621  cmp     rcx, rdi
0x140027624  jz      short loc_140027685
0x140027626  mov     eax, [rcx+2Ch]
0x140027629  test    al, 2
0x14002762b  jz      short loc_14002765D
0x14002762d  mov     rcx, [rcx+18h]
0x140027631  lea     rax, [rsp+240h+var_1E0]
0x140027636  mov     [rsp+240h+var_210], rax
0x14002763b  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140027642  mov     rax, [r14+40h]
0x140027646  mov     edx, 2Ah ; '*'
0x14002764b  mov     [rsp+240h+FirstName], rbx
0x140027650  mov     r9, r12
0x140027653  mov     [rsp+240h+var_220], rax
0x140027658  call    WPP_SF_ZZZZ
0x14002765d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027664  cmp     rcx, rdi
0x140027667  jz      short loc_140027685
0x140027669  mov     eax, [rcx+2Ch]
0x14002766c  test    al, 8
0x14002766e  jz      short loc_140027685
0x140027670  mov     edx, 2Bh ; '+'
0x140027675  mov     rcx, [rcx+18h]
0x140027679  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140027680  call    WPP_SF_
0x140027685  mov     rcx, [rbp+140h+var_50]
0x14002768c  xor     rcx, rsp; StackCookie
0x14002768f  call    __security_check_cookie
0x140027694  add     rsp, 208h
0x14002769b  pop     r15
0x14002769d  pop     r14
0x14002769f  pop     r13
0x1400276a1  pop     r12
0x1400276a3  pop     rdi
0x1400276a4  pop     rsi
0x1400276a5  pop     rbx
0x1400276a6  pop     rbp
0x1400276a7  retn
0x1400276a9  xorps   xmm0, xmm0
0x1400276ac  mov     byte ptr [rsp+240h+var_200], 0
0x1400276b1  movups  xmmword ptr [rbp+140h+var_1C0.Length], xmm0
0x1400276b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400276bc  lea     rax, WPP_GLOBAL_Control
0x1400276c3  cmp     rcx, rax
0x1400276c6  jz      short loc_1400276E7
0x1400276c8  mov     eax, [rcx+2Ch]
0x1400276cb  test    al, 2
0x1400276cd  jz      short loc_1400276E7
0x1400276cf  mov     rcx, [rcx+18h]
0x1400276d3  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400276da  mov     edx, 24h ; '$'
0x1400276df  mov     r9, rbx
0x1400276e2  call    WPP_SF_Z
0x1400276e7  mov     rcx, [rsi+0D8h]; FastMutex
0x1400276ee  xor     dil, dil
0x1400276f1  call    cs:__imp_ExAcquireFastMutex
0x1400276f8  nop     dword ptr [rax+rax+00h]
0x1400276fd  mov     rcx, [rsi+0E8h]; int
0x140027704  lea     rax, [rbp+140h+var_1C0]
0x140027708  mov     [rsp+240h+FirstName], rax; FirstName
0x14002770d  lea     r9, [rsp+240h+AuthenticationId]; int
0x140027712  lea     rax, [rsp+240h+var_200]
0x140027717  mov     rdx, rbx; int
0x14002771a  mov     [rsp+240h+var_220], rax; __int64
0x14002771f  call    MdaFindPrefixOfUnicodePrefix
0x140027724  test    al, al
0x140027726  jz      loc_1400277AE
0x14002772c  lea     r12, WPP_GLOBAL_Control
0x140027733  mov     rcx, cs:WPP_GLOBAL_Control
0x14002773a  cmp     rcx, r12
0x14002773d  jz      short loc_14002777B
0x14002773f  mov     eax, [rcx+2Ch]
0x140027742  test    al, 2
0x140027744  jz      short loc_14002777B
0x140027746  movzx   eax, byte ptr [rsp+240h+var_200]
0x14002774b  lea     r8, [rbp+140h+var_1C0]
0x14002774f  mov     r9, qword ptr [rsp+240h+AuthenticationId.LowPart]
0x140027754  mov     edx, 25h ; '%'
0x140027759  mov     rcx, [rcx+18h]
0x14002775d  mov     [rsp+240h+var_210], rbx
0x140027762  mov     [rsp+240h+FirstName], r8
0x140027767  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002776e  mov     r9, [r9+30h]
0x140027772  mov     dword ptr [rsp+240h+var_220], eax
0x140027776  call    WPP_SF_ZdZZ
0x14002777b  mov     rcx, [rsi+0E8h]; int
0x140027782  lea     rax, [rbp+140h+var_1C0]
0x140027786  mov     [rsp+240h+FirstName], rax; FirstName
0x14002778b  lea     r9, [rsp+240h+AuthenticationId]; int
0x140027790  lea     rax, [rsp+240h+var_200]
0x140027795  mov     rdx, rbx; int
0x140027798  mov     [rsp+240h+var_220], rax; __int64
0x14002779d  mov     dil, 1
0x1400277a0  call    MdaFindPrefixOfUnicodePrefix
0x1400277a5  test    al, al
0x1400277a7  jnz     short loc_140027733
0x1400277a9  mov     r12, qword ptr [rsp+240h+DestinationString.Length]
0x1400277ae  mov     rcx, [rsi+0D8h]; FastMutex
0x1400277b5  call    cs:__imp_ExReleaseFastMutex
0x1400277bc  nop     dword ptr [rax+rax+00h]
0x1400277c1  xor     esi, esi
0x1400277c3  test    dil, dil
0x1400277c6  jnz     loc_140027604
0x1400277cc  xorps   xmm0, xmm0
0x1400277cf  lea     r8d, [rsi+4Ch]; Size
0x1400277d3  xorps   xmm1, xmm1
0x1400277d6  lea     rcx, [rbp+140h+var_180]; void *
0x1400277da  xor     edx, edx; Val
0x1400277dc  movups  xmmword ptr [rsp+240h+DestinationString.Length], xmm0
0x1400277e1  movups  xmmword ptr [rsp+240h+SourceString.Length], xmm1
0x1400277e6  movups  [rbp+140h+var_1B0], xmm0
0x1400277ea  call    memset
0x1400277ef  xorps   xmm0, xmm0
0x1400277f2  mov     qword ptr [rsp+240h+AuthenticationId.LowPart], rsi
0x1400277f7  xor     edx, edx; Val
0x1400277f9  lea     r8d, [rsi+44h]; Size
0x1400277fd  lea     rcx, [rbp+140h+var_A0]; void *
0x140027804  movups  xmmword ptr [rbp+140h+SubjectContext.ClientToken], xmm0
0x140027808  movups  xmmword ptr [rbp+140h+SubjectContext.PrimaryToken], xmm0
0x14002780c  call    memset
0x140027811  xor     edx, edx; Val
0x140027813  lea     r8d, [rsi+58h]; Size
0x140027817  lea     rcx, [rbp+140h+var_120]; void *
0x14002781b  call    memset
0x140027820  mov     edx, 208h
0x140027825  mov     ecx, 102h
0x14002782a  mov     r8d, 3552664Eh
0x140027830  call    cs:__imp_ExAllocatePool2
0x140027837  nop     dword ptr [rax+rax+00h]
0x14002783c  mov     [rsp+240h+DestinationString.Buffer], rax
0x140027841  test    rax, rax
0x140027844  jz      loc_140027AAA
0x14002784a  movzx   eax, word ptr [rbx+2]
0x14002784e  mov     dil, 1
0x140027851  mov     [rsp+240h+SourceString.MaximumLength], ax
0x140027856  movzx   eax, word ptr [rbx]
0x140027859  mov     [rsp+240h+SourceString.Length], ax
0x14002785e  mov     rax, [rbx+8]
0x140027862  mov     [rsp+240h+SourceString.Buffer], rax
0x140027867  mov     dword ptr [rsp+240h+DestinationString.Length], 2080000h
0x14002786f  lea     rdx, [rsp+240h+SourceString]; SourceString
0x140027874  lea     rcx, [rsp+240h+DestinationString]; DestinationString
0x140027879  call    cs:__imp_RtlCopyUnicodeString
0x140027880  nop     dword ptr [rax+rax+00h]
0x140027885  movzx   edx, [rsp+240h+DestinationString.Length]
0x14002788a  mov     ecx, esi
0x14002788c  test    edx, 0FFFFFFFEh
0x140027892  jbe     short loc_1400278BA
0x140027894  mov     r8, [rsp+240h+DestinationString.Buffer]
0x140027899  mov     eax, ecx
0x14002789b  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1400278a1  jnz     short loc_1400278AF
0x1400278a3  mov     word ptr [r8+rax*2], 2Fh ; '/'
0x1400278aa  movzx   edx, [rsp+240h+DestinationString.Length]
0x1400278af  movzx   eax, dx
0x1400278b2  inc     ecx
0x1400278b4  shr     eax, 1
0x1400278b6  cmp     ecx, eax
0x1400278b8  jb      short loc_140027894
0x1400278ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400278c1  lea     rax, WPP_GLOBAL_Control
0x1400278c8  cmp     rcx, rax
0x1400278cb  jz      short loc_1400278EE
0x1400278cd  mov     eax, [rcx+2Ch]
0x1400278d0  test    al, 2
0x1400278d2  jz      short loc_1400278EE
0x1400278d4  mov     rcx, [rcx+18h]
0x1400278d8  lea     r9, [rsp+240h+DestinationString]
0x1400278dd  mov     edx, 26h ; '&'
  ... truncated ...
```
