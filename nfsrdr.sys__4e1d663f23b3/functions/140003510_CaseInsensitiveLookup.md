# CaseInsensitiveLookup

- ea: `0x140003510`
- end: `0x140003bc8`
- name: `CaseInsensitiveLookup`
- size: `1720`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, __int64, char, _QWORD *)`
- caller_count: `8`
- callee_count: `13`
- tags: ``

## callers

- `0x1400022c0`
- `0x1400070a0`
- `0x14000fbc0`
- `0x14001bbbc`
- `0x14001c694`
- `0x140030934`
- `0x140030ef0`
- `0x1400316d0`

## callees

- `0x140003510`
- `0x140004530`
- `0x140009380`
- `0x140013830`
- `0x140013dc0`
- `0x140014970`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x14002bb40`
- `0x14002bc4c`
- `0x14002c764`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000392d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000392d`
- `ntoskrnl!_strnicmp` at `0x1400038a5`
- `ntoskrnl!_strnicmp` at `0x1400038a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b75`
- `ntoskrnl!ExAllocatePool2` at `0x1400036e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400036e0`

## pseudocode

```c
__int64 __fastcall CaseInsensitiveLookup(__int64 a1, __int64 a2, unsigned __int16 *a3, __int64 a4, char a5, _QWORD *a6)
{
  int v6; // r15d
  int v8; // r14d
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // ebx
  _QWORD *v14; // r13
  char v15; // r12
  int DirectoryEntry; // r15d
  char *Pool2; // rax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // edx
  int v21; // esi
  int v22; // ecx
  char *v23; // r8
  char *v24; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-79h] BYREF
  char *Str1; // [rsp+60h] [rbp-69h] BYREF
  char *v27; // [rsp+68h] [rbp-61h] BYREF
  struct _STRING v28; // [rsp+70h] [rbp-59h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-49h] BYREF
  char *Str2[2]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-29h]
  __int64 v32; // [rsp+A8h] [rbp-21h] BYREF
  void *v33; // [rsp+B0h] [rbp-19h]
  UNICODE_STRING SourceString; // [rsp+B8h] [rbp-11h] BYREF
  _OWORD v35[4]; // [rsp+C8h] [rbp-1h] BYREF
  int v36; // [rsp+120h] [rbp+57h] BYREF
  PVOID P; // [rsp+128h] [rbp+5Fh]
  __int64 v38; // [rsp+138h] [rbp+6Fh]

  v38 = a4;
  v31 = *(_QWORD *)(a2 + 80);
  v6 = a4;
  Str1 = 0;
  v32 = 0;
  v8 = a2;
  v36 = 0;
  SourceString = 0;
  v35[0] = 0;
  *(_OWORD *)Src = 0;
  DestinationString = 0;
  *(_OWORD *)Str2 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_cca3db0522623f5e31396e1525c29988_Traceguids, a3);
  v10 = *(_QWORD *)(a1 + 40);
  if ( !v10 )
    return 3221225662LL;
  v11 = *(_QWORD *)(a1 + 32);
  if ( !*(_QWORD *)(v11 + 40) || !*(_QWORD *)(*(_QWORD *)(v11 + 32) + 32LL) )
    return 3221225662LL;
  if ( !*a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    v12 = NfsLookup(a1, v8, (_DWORD)a3, v6, a5, (__int64)a6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    return v12;
  }
  if ( (*(_DWORD *)(v10 + 32) & 0x80u) == 0 )
  {
    v14 = a6;
    DirectoryEntry = -1073741809;
    v15 = a5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_cca3db0522623f5e31396e1525c29988_Traceguids, a3);
    v14 = a6;
    v15 = a5;
    DirectoryEntry = NfsLookup(a1, v8, (_DWORD)a3, v6, a5, (__int64)a6);
    if ( DirectoryEntry >= 0 )
    {
LABEL_52:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
      }
      return 0;
    }
  }
  Pool2 = (char *)ExAllocatePool2(258, 1552, 844260942);
  P = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    DirectoryEntry = -1073741670;
    goto LABEL_71;
  }
  if ( DirectoryEntry != -1073741809 || (*(_DWORD *)(v10 + 32) & 0x100) == 0 || !v15 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_70;
    v19 = 31;
    goto LABEL_69;
  }
  LODWORD(Str2[0]) = 0x1000000;
  v33 = Pool2 + 512;
  Str2[1] = Pool2 + 512;
  MdaDissectNameTail(a3, (__int64)&SourceString, (__int64)v35);
  DirectoryEntry = NfsConvertUnicodeToAnsi(v31, Str2, v35);
  if ( DirectoryEntry >= 0 )
  {
    DirectoryEntry = 0;
    v20 = *(_DWORD *)(v10 + 24);
    v21 = v38;
    v22 = (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL) + 88LL) != 2) + 1;
    v23 = (char *)P + 1024;
    v27 = (char *)P + 1024;
    v24 = (char *)P + 1288;
    *((_DWORD *)P + 278) = 0;
    *((_QWORD *)v23 + 32) = v24;
    *(_DWORD *)v23 = v22;
    *((_DWORD *)v23 + 5) = -1;
    *((_WORD *)v23 + 8) = -1;
    *((_QWORD *)v23 + 3) = 0;
    *((_QWORD *)v23 + 4) = 0;
    *((_DWORD *)v23 + 1) = v20;
    *((_QWORD *)v23 + 1) = 0;
    *((_QWORD *)v23 + 10) = 0;
    *((_QWORD *)v23 + 8) = 0;
    *((_DWORD *)v23 + 12) = 7;
    *((_QWORD *)v23 + 7) = 0;
    while ( DirectoryEntry >= 0 )
    {
      DirectoryEntry = NfsReadDirectoryEntry(
                         a1,
                         v8,
                         v21,
                         (unsigned int)&v27,
                         0,
                         (__int64)&v32,
                         (__int64)&Str1,
                         (__int64)&v36,
                         0,
                         0);
      if ( DirectoryEntry >= 0 && v36 == LOWORD(Str2[0]) && !_strnicmp(Str1, Str2[1], LOWORD(Str2[0])) )
      {
        v28.Buffer = Str1;
        v28.Length = v36;
        v28.MaximumLength = v36;
        if ( (*(_DWORD *)(v10 + 32) & 0x40) != 0 )
        {
          DsEucToSjis(Str1);
        }
        else if ( (*(_DWORD *)(v10 + 32) & 0x6000) == 0x2000 )
        {
          DsEucToCns(Str1, (unsigned __int16)v36, Str1, &v28);
        }
        DestinationString.Length = 0;
        DestinationString.MaximumLength = SourceString.Length + 2 * (v28.Length + 2);
        DestinationString.Buffer = (PWSTR)P;
        RtlCopyUnicodeString(&DestinationString, &SourceString);
        Src[1] = v33;
        LODWORD(Src[0]) = 0x2000000;
        DirectoryEntry = NfsConvertAnsiToUnicode(v31, (struct _UNICODE_STRING *)Src, &v28, 0, *(_DWORD *)(v10 + 32));
        if ( DirectoryEntry < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
          }
LABEL_65:
          NfsReadDirectoryQuit(&v27, 0);
          goto LABEL_70;
        }
        DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
        DestinationString.Length += 2;
        memmove(&DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1], Src[1], LOWORD(Src[0]));
        DestinationString.Length += LOWORD(Src[0]);
        DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
        NfsReadDirectoryQuit(&v27, 0);
        DirectoryEntry = NfsLookup(a1, v8, (unsigned int)&DestinationString, v21, v15, (__int64)v14);
        if ( DirectoryEntry >= 0 )
        {
          ExFreePoolWithTag(P, 0);
          goto LABEL_52;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          v19 = 34;
          goto LABEL_69;
        }
        goto LABEL_70;
      }
    }
    if ( DirectoryEntry != -2147483642 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
      }
      goto LABEL_65;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
    DirectoryEntry = -1073741809;
    goto LABEL_70;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v19 = 32;
LABEL_69:
    WPP_SF_d(v18->AttachedDevice, v19, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  }
LABEL_70:
  ExFreePoolWithTag(P, 0);
  *v14 = 0;
LABEL_71:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  return (unsigned int)DirectoryEntry;
}

```

## disassembly

```asm
0x140003510  mov     [rsp-8+arg_18], r9
0x140003515  push    rbp
0x140003516  push    rbx
0x140003517  push    rsi
0x140003518  push    rdi
0x140003519  push    r12
0x14000351b  push    r14
0x14000351d  push    r15
0x14000351f  lea     rbp, [rsp-17h]
0x140003524  sub     rsp, 0E0h
0x14000352b  mov     rax, [rdx+50h]
0x14000352f  xorps   xmm0, xmm0
0x140003532  xorps   xmm1, xmm1
0x140003535  mov     [rbp+47h+var_70], rax
0x140003539  xor     eax, eax
0x14000353b  mov     r15, r9
0x14000353e  mov     [rbp+47h+Str1], rax
0x140003542  mov     rsi, r8
0x140003545  mov     [rbp+47h+var_68], rax
0x140003549  mov     r14, rdx
0x14000354c  mov     [rbp+47h+arg_0], eax
0x14000354f  mov     rbx, rcx
0x140003552  movups  xmmword ptr [rbp+47h+SourceString.Length], xmm0
0x140003556  movups  [rbp+47h+var_48], xmm1
0x14000355a  movups  xmmword ptr [rbp+47h+Src], xmm0
0x14000355e  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x140003562  movups  xmmword ptr [rbp+47h+Str2], xmm0
0x140003566  movups  [rbp+47h+var_A0], xmm1
0x14000356a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003571  lea     r12, WPP_GLOBAL_Control
0x140003578  cmp     rcx, r12
0x14000357b  jz      short loc_14000359E
0x14000357d  test    dword ptr [rcx+2Ch], 400h
0x140003584  jz      short loc_14000359E
0x140003586  mov     rcx, [rcx+18h]
0x14000358a  mov     r9, r8
0x14000358d  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003594  mov     edx, 1Ah
0x140003599  call    WPP_SF_Z
0x14000359e  mov     rdi, [rbx+28h]
0x1400035a2  test    rdi, rdi
0x1400035a5  jz      loc_140003BBE
0x1400035ab  mov     rax, [rbx+20h]
0x1400035af  cmp     qword ptr [rax+28h], 0
0x1400035b4  jz      loc_140003BBE
0x1400035ba  mov     rax, [rax+20h]
0x1400035be  cmp     qword ptr [rax+20h], 0
0x1400035c3  jz      loc_140003BBE
0x1400035c9  cmp     word ptr [rsi], 0
0x1400035cd  jnz     loc_140003655
0x1400035d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035da  cmp     rcx, r12
0x1400035dd  jz      short loc_1400035FD
0x1400035df  test    dword ptr [rcx+2Ch], 400h
0x1400035e6  jz      short loc_1400035FD
0x1400035e8  mov     rcx, [rcx+18h]
0x1400035ec  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x1400035f3  mov     edx, 1Bh
0x1400035f8  call    WPP_SF_
0x1400035fd  mov     rax, [rbp+47h+arg_28]
0x140003601  mov     r9, r15
0x140003604  mov     [rsp+110h+var_E8], rax
0x140003609  mov     r8, rsi
0x14000360c  movzx   eax, [rbp+47h+arg_20]
0x140003610  mov     rdx, r14
0x140003613  mov     rcx, rbx
0x140003616  mov     byte ptr [rsp+110h+var_F0], al
0x14000361a  call    NfsLookup
0x14000361f  mov     ebx, eax
0x140003621  mov     rcx, cs:WPP_GLOBAL_Control
0x140003628  cmp     rcx, r12
0x14000362b  jz      short loc_14000364E
0x14000362d  test    dword ptr [rcx+2Ch], 400h
0x140003634  jz      short loc_14000364E
0x140003636  mov     rcx, [rcx+18h]
0x14000363a  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003641  mov     edx, 1Ch
0x140003646  mov     r9d, eax
0x140003649  call    WPP_SF_d
0x14000364e  mov     eax, ebx
0x140003650  jmp     loc_140003AA7
0x140003655  mov     eax, [rdi+20h]
0x140003658  mov     [rsp+110h+arg_10], r13
0x140003660  test    al, al
0x140003662  jns     short loc_1400036C1
0x140003664  mov     rcx, cs:WPP_GLOBAL_Control
0x14000366b  cmp     rcx, r12
0x14000366e  jz      short loc_140003691
0x140003670  test    dword ptr [rcx+2Ch], 400h
0x140003677  jz      short loc_140003691
0x140003679  mov     rcx, [rcx+18h]
0x14000367d  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003684  mov     edx, 1Dh
0x140003689  mov     r9, rsi
0x14000368c  call    WPP_SF_Z
0x140003691  mov     r13, [rbp+47h+arg_28]
0x140003695  mov     r9, r15
0x140003698  movzx   r12d, [rbp+47h+arg_20]
0x14000369d  mov     r8, rsi
0x1400036a0  mov     [rsp+110h+var_E8], r13
0x1400036a5  mov     rdx, r14
0x1400036a8  mov     rcx, rbx
0x1400036ab  mov     byte ptr [rsp+110h+var_F0], r12b
0x1400036b0  call    NfsLookup
0x1400036b5  mov     r15d, eax
0x1400036b8  test    eax, eax
0x1400036ba  js      short loc_1400036D0
0x1400036bc  jmp     loc_140003A6C
0x1400036c1  mov     r13, [rbp+47h+arg_28]
0x1400036c5  mov     r15d, 0C000000Fh
0x1400036cb  movzx   r12d, [rbp+47h+arg_20]
0x1400036d0  mov     edx, 610h
0x1400036d5  mov     ecx, 102h
0x1400036da  mov     r8d, 3252664Eh
0x1400036e0  call    cs:__imp_ExAllocatePool2
0x1400036e7  nop     dword ptr [rax+rax+00h]
0x1400036ec  mov     [rbp+47h+P], rax
0x1400036f0  test    rax, rax
0x1400036f3  jnz     short loc_14000372F
0x1400036f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036fc  lea     rbx, WPP_GLOBAL_Control
0x140003703  cmp     rcx, rbx
0x140003706  jz      short loc_140003724
0x140003708  mov     eax, [rcx+2Ch]
0x14000370b  test    al, 1
0x14000370d  jz      short loc_140003724
0x14000370f  mov     rcx, [rcx+18h]
0x140003713  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14000371a  mov     edx, 1Eh
0x14000371f  call    WPP_SF_
0x140003724  mov     r15d, 0C000009Ah
0x14000372a  jmp     loc_140003B89
0x14000372f  cmp     r15d, 0C000000Fh
0x140003736  jnz     loc_140003B3D
0x14000373c  mov     edx, 100h
0x140003741  test    [rdi+20h], edx
0x140003744  jz      loc_140003B3D
0x14000374a  test    r12b, r12b
0x14000374d  jz      loc_140003B3D
0x140003753  add     rax, 200h
0x140003759  mov     dword ptr [rbp+47h+Str2], 1000000h
0x140003760  lea     r8, [rbp+47h+var_48]
0x140003764  mov     [rbp+47h+var_60], rax
0x140003768  lea     rdx, [rbp+47h+SourceString]
0x14000376c  mov     [rbp+47h+Str2+8], rax
0x140003770  mov     rcx, rsi
0x140003773  call    MdaDissectNameTail
0x140003778  mov     r11d, [rdi+20h]
0x14000377c  lea     r8, [rbp+47h+var_48]
0x140003780  mov     rcx, [rbp+47h+var_70]
0x140003784  lea     rdx, [rbp+47h+Str2]
0x140003788  mov     [rsp+110h+var_F0], r11d
0x14000378d  call    NfsConvertUnicodeToAnsi
0x140003792  mov     r15d, eax
0x140003795  test    eax, eax
0x140003797  jns     short loc_1400037C5
0x140003799  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037a0  lea     rbx, WPP_GLOBAL_Control
0x1400037a7  cmp     rcx, rbx
0x1400037aa  jz      loc_140003B6F
0x1400037b0  mov     eax, [rcx+2Ch]
0x1400037b3  test    al, 1
0x1400037b5  jz      loc_140003B6F
0x1400037bb  mov     edx, 20h ; ' '
0x1400037c0  jmp     loc_140003B5C
0x1400037c5  mov     rax, [rbx+20h]
0x1400037c9  xor     r15d, r15d
0x1400037cc  mov     edx, [rdi+18h]
0x1400037cf  mov     r8, [rbp+47h+P]
0x1400037d3  mov     rsi, [rbp+47h+arg_18]
0x1400037d7  mov     rcx, [rax+20h]
0x1400037db  mov     rax, [rcx+20h]
0x1400037df  xor     ecx, ecx
0x1400037e1  cmp     dword ptr [rax+58h], 2
0x1400037e5  setnz   cl
0x1400037e8  inc     ecx
0x1400037ea  add     r8, 400h
0x1400037f1  mov     [rbp+47h+var_A8], r8
0x1400037f5  lea     rax, [r8+108h]
0x1400037fc  mov     [r8+58h], r15d
0x140003800  mov     [r8+100h], rax
0x140003807  mov     [r8], ecx
0x14000380a  mov     dword ptr [r8+14h], 0FFFFFFFFh
0x140003812  mov     word ptr [r8+10h], 0FFFFh
0x140003819  mov     [r8+18h], r15
0x14000381d  mov     [r8+20h], r15
0x140003821  mov     [r8+4], edx
0x140003825  mov     [r8+8], r15
0x140003829  mov     [r8+50h], r15
0x14000382d  mov     [r8+40h], r15
0x140003831  mov     dword ptr [r8+30h], 7
0x140003839  mov     [r8+38h], r15
0x14000383d  test    r15d, r15d
0x140003840  js      loc_140003ABA
0x140003846  mov     [rsp+110h+var_C8], 0
0x14000384f  lea     rax, [rbp+47h+arg_0]
0x140003853  mov     [rsp+110h+var_D0], 0
0x14000385c  lea     r9, [rbp+47h+var_A8]
0x140003860  mov     [rsp+110h+var_D8], rax
0x140003865  mov     r8, rsi
0x140003868  lea     rax, [rbp+47h+Str1]
0x14000386c  mov     rdx, r14
0x14000386f  mov     [rsp+110h+var_E0], rax
0x140003874  mov     rcx, rbx
0x140003877  lea     rax, [rbp+47h+var_68]
0x14000387b  mov     [rsp+110h+var_E8], rax
0x140003880  mov     byte ptr [rsp+110h+var_F0], 0
0x140003885  call    NfsReadDirectoryEntry
0x14000388a  mov     r15d, eax
0x14000388d  test    eax, eax
0x14000388f  js      short loc_14000383D
0x140003891  movzx   ecx, word ptr [rbp+47h+Str2]
0x140003895  cmp     [rbp+47h+arg_0], ecx
0x140003898  jnz     short loc_14000383D
0x14000389a  mov     rdx, [rbp+47h+Str2+8]; Str2
0x14000389e  mov     r8d, ecx; MaxCount
0x1400038a1  mov     rcx, [rbp+47h+Str1]; Str1
0x1400038a5  call    cs:__imp__strnicmp
0x1400038ac  nop     dword ptr [rax+rax+00h]
0x1400038b1  test    eax, eax
0x1400038b3  jnz     short loc_14000383D
0x1400038b5  mov     ecx, [rbp+47h+arg_0]
0x1400038b8  mov     rax, [rbp+47h+Str1]
0x1400038bc  mov     qword ptr [rbp+47h+var_A0+8], rax
0x1400038c0  mov     word ptr [rbp+47h+var_A0], cx
0x1400038c4  mov     word ptr [rbp+47h+var_A0+2], cx
0x1400038c8  mov     edx, [rdi+20h]
0x1400038cb  test    dl, 40h
0x1400038ce  jz      short loc_1400038E4
0x1400038d0  movzx   edx, cx
0x1400038d3  lea     r9, [rbp+47h+var_A0]
0x1400038d7  mov     rcx, rax; Src
0x1400038da  mov     r8, rax
0x1400038dd  call    DsEucToSjis
0x1400038e2  jmp     short loc_140003904
0x1400038e4  and     edx, 6000h
0x1400038ea  cmp     edx, 2000h
0x1400038f0  jnz     short loc_140003904
0x1400038f2  movzx   edx, cx
0x1400038f5  lea     r9, [rbp+47h+var_A0]
0x1400038f9  mov     rcx, rax
0x1400038fc  mov     r8, rax
0x1400038ff  call    DsEucToCns
0x140003904  xor     eax, eax
0x140003906  lea     rdx, [rbp+47h+SourceString]; SourceString
0x14000390a  mov     [rbp+47h+DestinationString.Length], ax
0x14000390e  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x140003912  movzx   eax, word ptr [rbp+47h+var_A0]
0x140003916  add     ax, 2
0x14000391a  add     ax, ax
0x14000391d  add     ax, [rbp+47h+SourceString.Length]
0x140003921  mov     [rbp+47h+DestinationString.MaximumLength], ax
0x140003925  mov     rax, [rbp+47h+P]
0x140003929  mov     [rbp+47h+DestinationString.Buffer], rax
0x14000392d  call    cs:__imp_RtlCopyUnicodeString
0x140003934  nop     dword ptr [rax+rax+00h]
0x140003939  mov     rax, [rbp+47h+var_60]
0x14000393d  lea     r8, [rbp+47h+var_A0]
0x140003941  mov     rcx, [rbp+47h+var_70]
0x140003945  lea     rdx, [rbp+47h+Src]
0x140003949  mov     [rbp+47h+Src+8], rax
0x14000394d  xor     r9d, r9d
0x140003950  mov     dword ptr [rbp+47h+Src], 2000000h
0x140003957  mov     eax, [rdi+20h]
0x14000395a  mov     [rsp+110h+var_F0], eax
0x14000395e  call    NfsConvertAnsiToUnicode
0x140003963  mov     r15d, eax
0x140003966  test    eax, eax
0x140003968  jns     short loc_1400039A6
0x14000396a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003971  lea     rbx, WPP_GLOBAL_Control
0x140003978  cmp     rcx, rbx
0x14000397b  jz      loc_140003B30
0x140003981  mov     eax, [rcx+2Ch]
0x140003984  test    al, 1
0x140003986  jz      loc_140003B30
0x14000398c  mov     rcx, [rcx+18h]
0x140003990  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003997  mov     edx, 21h ; '!'
0x14000399c  call    WPP_SF_
0x1400039a1  jmp     loc_140003B30
0x1400039a6  movzx   ecx, [rbp+47h+DestinationString.Length]
0x1400039aa  mov     rax, [rbp+47h+DestinationString.Buffer]
0x1400039ae  shr     rcx, 1
0x1400039b1  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400039b7  movzx   eax, [rbp+47h+DestinationString.Length]
0x1400039bb  movzx   r8d, word ptr [rbp+47h+Src]; Size
0x1400039c0  add     ax, 2
0x1400039c4  mov     rdx, [rbp+47h+Src+8]; Src
0x1400039c8  movzx   ecx, ax
0x1400039cb  mov     [rbp+47h+DestinationString.Length], ax
0x1400039cf  mov     rax, [rbp+47h+DestinationString.Buffer]
0x1400039d3  shr     rcx, 1
0x1400039d6  lea     rcx, [rax+rcx*2]; void *
0x1400039da  call    memmove
0x1400039df  movzx   eax, word ptr [rbp+47h+Src]
0x1400039e3  xor     ecx, ecx
0x1400039e5  add     ax, [rbp+47h+DestinationString.Length]
0x1400039e9  movzx   edx, ax
0x1400039ec  mov     rax, [rbp+47h+DestinationString.Buffer]
  ... truncated ...
```
