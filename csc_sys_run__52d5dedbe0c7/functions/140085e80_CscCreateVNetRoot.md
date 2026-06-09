# CscCreateVNetRoot

- ea: `0x140085e80`
- end: `0x140086442`
- name: `CscCreateVNetRoot`
- size: `1474`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x14000a4f0`
- `0x14000a634`
- `0x14000f8b0`
- `0x1400119d0`
- `0x1400169d4`
- `0x140016a04`
- `0x140018930`
- `0x1400190ec`
- `0x14001b710`
- `0x14001d854`
- `0x14001d920`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`
- `0x14004fbe0`
- `0x140085e80`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400860ba`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400860ba`
- `rdbss!RxUpdateNetRootCachingMode` at `0x1400861bc`
- `rdbss!RxUpdateNetRootCachingMode` at `0x1400861bc`
- `rdbss!RxQueryNetRootCachingMode` at `0x140086192`
- `rdbss!RxQueryNetRootCachingMode` at `0x140086224`
- `rdbss!RxQueryNetRootCachingMode` at `0x140086192`
- `rdbss!RxQueryNetRootCachingMode` at `0x140086224`

## pseudocode

```c
__int64 __fastcall CscCreateVNetRoot(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r13
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  char v7; // si
  int InformationEntry; // ebx
  int v9; // r14d
  bool v10; // r12
  int v11; // r14d
  int Entry; // eax
  void (__fastcall *v13)(__int64); // rax
  unsigned int v15; // eax
  __int64 v16; // r9
  int v17; // [rsp+40h] [rbp-79h]
  __int64 v18; // [rsp+48h] [rbp-71h] BYREF
  int v19; // [rsp+50h] [rbp-69h]
  __int64 v20; // [rsp+58h] [rbp-61h]
  __int64 v21; // [rsp+60h] [rbp-59h]
  _DWORD v22[20]; // [rsp+70h] [rbp-49h] BYREF

  v1 = *(_QWORD *)(a1 + 264);
  v20 = *(_QWORD *)(a1 + 32);
  v18 = 0;
  v3 = *(_QWORD *)(v1 + 32);
  v21 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 40LL);
  memset(v22, 0, sizeof(v22));
  v7 = 0;
  InformationEntry = -1073741634;
  v9 = *(_DWORD *)(v20 + 120);
  v10 = *(_QWORD *)a1 != (_QWORD)CscDeviceObject;
  v17 = -1073741634;
  v19 = *(_DWORD *)(v20 + 256);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v6) = v10 ? 89 : 78;
    WPP_SF_cqqZ(WPP_GLOBAL_Control->AttachedDevice, v4, v5, v6, v1, v3, *(_QWORD *)(v3 + 88));
  }
  if ( !v10 )
    goto LABEL_3;
  InformationEntry = *(_DWORD *)(a1 + 284);
  if ( !InformationEntry )
    InformationEntry = *(_DWORD *)(a1 + 280);
  v17 = InformationEntry;
  v7 = CscTransitnOKToGoOffline((unsigned int)InformationEntry);
  if ( !v7 )
    v7 = ((v9 & 0x100) != 0 || (*(_DWORD *)(v1 + 100) & 1) != 0)
      && (InformationEntry == -1073741790
       || InformationEntry == -1073741724
       || InformationEntry == -1073741718
       || InformationEntry == -1073741715
       || InformationEntry == -1073741711
       || InformationEntry == -1073741276
       || InformationEntry == -1073740920);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v16) = v7 != 0 ? 89 : 78;
    WPP_SF_cDD(
      WPP_GLOBAL_Control->AttachedDevice,
      35,
      WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      v16,
      *(_DWORD *)(a1 + 284),
      *(_DWORD *)(a1 + 280));
  }
  if ( !v7 || (unsigned __int16)RxQueryNetRootCachingMode(v3) != 12 )
  {
LABEL_3:
    v11 = 0;
    if ( v21
      && (*(_BYTE *)(v21 + 4) & 1) != 0
      && RtlEqualUnicodeString(*(PCUNICODE_STRING *)(v3 + 88), &CscDclMRxPrefixes, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
      InformationEntry = 0;
      goto LABEL_14;
    }
    if ( !v10 || v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
      Entry = CscStoreFindOrCreateEntry(
                (unsigned int)&v18,
                0,
                0,
                (int)a1 + 120,
                *(_QWORD *)(a1 + 40) != 0 ? 8 : 0,
                0,
                0,
                *(_QWORD *)(a1 + 40));
      InformationEntry = Entry;
      if ( Entry < 0 )
      {
        if ( Entry == -1073741790 )
          goto LABEL_15;
        if ( (*(_BYTE *)(v20 + 749) & 0x20) == 0 || (*(_DWORD *)(v20 + 120) & 0x800) == 0 )
        {
          InformationEntry = v17;
          v11 = 1425;
          goto LABEL_13;
        }
        InformationEntry = 0;
        v11 = 1420;
LABEL_14:
        *(_BYTE *)(v3 + 77) = 0;
        *(_DWORD *)(v3 + 80) = 7;
        goto LABEL_15;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v18);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
        }
      }
      InformationEntry = CscStoreQueryInformationEntryEx(v18, 0, (__int64)v22, 0, 0, 0, 0);
      if ( InformationEntry < 0 )
      {
        v11 = 1328;
        goto LABEL_15;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v18);
      if ( ((v22[0] & 0x800000) != 0 || (v22[0] & 0x10000) != 0) && (v19 & 0x228) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v22[0]);
        }
        InformationEntry = v17;
      }
      CscStoreDereferenceEntry(&v18);
      if ( (unsigned int)RxQueryNetRootCachingMode(v3) == -1 )
      {
        if ( InformationEntry >= 0 )
        {
          v15 = CscConvertStoreCacheModeToSmbCacheMode(v22[2]);
          RxUpdateNetRootCachingMode(v3, v15);
          goto LABEL_14;
        }
LABEL_15:
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_qqq(
              WPP_GLOBAL_Control->AttachedDevice,
              43,
              WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
              v18,
              0,
              0);
          }
          CscStoreDereferenceEntry(&v18);
        }
        goto LABEL_16;
      }
    }
LABEL_13:
    if ( InformationEntry < 0 )
      goto LABEL_15;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
  v11 = 1260;
LABEL_16:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      (unsigned int)InformationEntry,
      v11);
  v13 = *(void (__fastcall **)(__int64))(a1 + 272);
  *(_DWORD *)(a1 + 284) = InformationEntry;
  *(_DWORD *)(a1 + 280) = InformationEntry;
  v13(a1);
  return 259;
}

```

## disassembly

```asm
0x140085e80  push    rbp
0x140085e82  push    rbx
0x140085e83  push    rsi
0x140085e84  push    rdi
0x140085e85  push    r12
0x140085e87  push    r13
0x140085e89  push    r14
0x140085e8b  push    r15
0x140085e8d  lea     rbp, [rsp-1Fh]
0x140085e92  sub     rsp, 0D8h
0x140085e99  mov     rax, cs:__security_cookie
0x140085ea0  xor     rax, rsp
0x140085ea3  mov     [rbp+57h+var_50], rax
0x140085ea7  mov     rdi, [rcx+108h]
0x140085eae  mov     r15, rcx
0x140085eb1  mov     r14, [rcx+20h]
0x140085eb5  xor     edx, edx; Val
0x140085eb7  mov     [rbp+57h+var_B8], r14
0x140085ebb  mov     [rbp+57h+var_C8], 0
0x140085ec3  mov     r13, [rdi+20h]
0x140085ec7  lea     r8d, [rdx+50h]; Size
0x140085ecb  mov     rax, [r13+20h]
0x140085ecf  mov     rcx, [rax+28h]
0x140085ed3  mov     [rbp+57h+var_B0], rcx
0x140085ed7  lea     rcx, [rbp+57h+var_A0]; void *
0x140085edb  call    memset
0x140085ee0  mov     rax, cs:CscDeviceObject
0x140085ee7  xor     sil, sil
0x140085eea  cmp     [r15], rax
0x140085eed  mov     ebx, 0C00000BEh
0x140085ef2  mov     rax, [rbp+57h+var_B8]
0x140085ef6  mov     r14d, [r14+78h]
0x140085efa  setnz   r12b
0x140085efe  mov     [rbp+57h+var_D0], ebx
0x140085f01  mov     eax, [rax+100h]
0x140085f07  mov     [rbp+57h+var_C0], eax
0x140085f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140085f11  lea     rax, WPP_GLOBAL_Control
0x140085f18  cmp     rcx, rax
0x140085f1b  jnz     loc_140086070
0x140085f21  test    r12b, r12b
0x140085f24  jnz     loc_1400861CD
0x140085f2a  mov     rax, [rbp+57h+var_B0]
0x140085f2e  xor     r14d, r14d
0x140085f31  test    rax, rax
0x140085f34  jz      short loc_140085F40
0x140085f36  test    byte ptr [rax+4], 1
0x140085f3a  jnz     loc_1400860AC
0x140085f40  mov     dil, 40h ; '@'
0x140085f43  test    r12b, r12b
0x140085f46  jz      short loc_140085F5C
0x140085f48  xor     r12d, r12d
0x140085f4b  test    sil, sil
0x140085f4e  jnz     short loc_140085F5F
0x140085f50  lea     rsi, WPP_GLOBAL_Control
0x140085f57  jmp     loc_140085FDE
0x140085f5c  xor     r12d, r12d
0x140085f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140085f66  lea     rsi, WPP_GLOBAL_Control
0x140085f6d  cmp     rcx, rsi
0x140085f70  jnz     loc_1400860FB
0x140085f76  mov     rcx, [r15+28h]
0x140085f7a  lea     r9, [r15+78h]
0x140085f7e  mov     [rsp+110h+var_D8], rcx
0x140085f83  mov     rax, rcx
0x140085f86  neg     rax
0x140085f89  mov     [rsp+110h+var_E0], r12
0x140085f8e  mov     [rsp+110h+var_E8], r12
0x140085f93  lea     rcx, [rbp+57h+var_C8]
0x140085f97  sbb     edx, edx
0x140085f99  xor     r8d, r8d
0x140085f9c  and     edx, 8
0x140085f9f  mov     dword ptr [rsp+110h+var_F0], edx
0x140085fa3  xor     edx, edx
0x140085fa5  call    CscStoreFindOrCreateEntry
0x140085faa  mov     ebx, eax
0x140085fac  test    eax, eax
0x140085fae  jns     loc_140086121
0x140085fb4  cmp     eax, 0C0000022h
0x140085fb9  jz      short loc_140085FEE
0x140085fbb  mov     rcx, [rbp+57h+var_B8]
0x140085fbf  test    byte ptr [rcx+2EDh], 20h
0x140085fc6  jz      short loc_140085FD5
0x140085fc8  test    dword ptr [rcx+78h], 800h
0x140085fcf  jnz     loc_1400863F3
0x140085fd5  mov     ebx, [rbp+57h+var_D0]
0x140085fd8  mov     r14d, 591h
0x140085fde  test    ebx, ebx
0x140085fe0  js      short loc_140085FEE
0x140085fe2  mov     [r13+4Dh], r12b
0x140085fe6  mov     dword ptr [r13+50h], 7
0x140085fee  mov     r9, [rbp+57h+var_C8]
0x140085ff2  test    r9, r9
0x140085ff5  jnz     loc_140086401
0x140085ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140086002  cmp     rcx, rsi
0x140086005  jnz     short loc_14008604A
0x140086007  mov     rax, [r15+110h]
0x14008600e  mov     rcx, r15
0x140086011  mov     [r15+11Ch], ebx
0x140086018  mov     [r15+118h], ebx
0x14008601f  call    _guard_dispatch_icall
0x140086024  mov     eax, 103h
0x140086029  mov     rcx, [rbp+57h+var_50]
0x14008602d  xor     rcx, rsp; StackCookie
0x140086030  call    __security_check_cookie
0x140086035  add     rsp, 0D8h
0x14008603c  pop     r15
0x14008603e  pop     r14
0x140086040  pop     r13
0x140086042  pop     r12
0x140086044  pop     rdi
0x140086045  pop     rsi
0x140086046  pop     rbx
0x140086047  pop     rbp
0x140086048  retn
0x14008604a  mov     eax, [rcx+2Ch]
0x14008604d  test    al, 20h
0x14008604f  jz      short loc_140086007
0x140086051  mov     rcx, [rcx+18h]
0x140086055  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008605c  mov     edx, 2Ch ; ','
0x140086061  mov     dword ptr [rsp+110h+var_F0], r14d
0x140086066  mov     r9d, ebx
0x140086069  call    WPP_SF_Dd
0x14008606e  jmp     short loc_140086007
0x140086070  mov     eax, [rcx+2Ch]
0x140086073  test    al, 20h
0x140086075  jz      loc_140085F21
0x14008607b  mov     rcx, [rcx+18h]
0x14008607f  mov     al, r12b
0x140086082  neg     al
0x140086084  mov     rax, [r13+58h]
0x140086088  sbb     r9b, r9b
0x14008608b  mov     [rsp+110h+var_E0], rax
0x140086090  and     r9b, 0Bh
0x140086094  mov     [rsp+110h+var_E8], r13
0x140086099  add     r9b, 4Eh ; 'N'
0x14008609d  mov     [rsp+110h+var_F0], rdi
0x1400860a2  call    WPP_SF_cqqZ
0x1400860a7  jmp     loc_140085F21
0x1400860ac  mov     rcx, [r13+58h]; String1
0x1400860b0  lea     rdx, CscDclMRxPrefixes; String2
0x1400860b7  xor     r8d, r8d; CaseInSensitive
0x1400860ba  call    cs:__imp_RtlEqualUnicodeString
0x1400860c1  nop     dword ptr [rax+rax+00h]
0x1400860c6  test    al, al
0x1400860c8  jz      loc_140085F40
0x1400860ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400860d5  lea     rsi, WPP_GLOBAL_Control
0x1400860dc  mov     dil, 40h ; '@'
0x1400860df  cmp     rcx, rsi
0x1400860e2  jz      short loc_1400860F0
0x1400860e4  mov     eax, [rcx+2Ch]
0x1400860e7  test    dil, al
0x1400860ea  jnz     loc_140086310
0x1400860f0  xor     r12d, r12d
0x1400860f3  mov     ebx, r12d
0x1400860f6  jmp     loc_140085FE2
0x1400860fb  mov     eax, [rcx+2Ch]
0x1400860fe  test    dil, al
0x140086101  jz      loc_140085F76
0x140086107  mov     rcx, [rcx+18h]
0x14008610b  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140086112  mov     edx, 26h ; '&'
0x140086117  call    WPP_SF_
0x14008611c  jmp     loc_140085F76
0x140086121  mov     rcx, cs:WPP_GLOBAL_Control
0x140086128  cmp     rcx, rsi
0x14008612b  jnz     loc_14008632A
0x140086131  mov     rcx, [rbp+57h+var_C8]
0x140086135  lea     r8, [rbp+57h+var_A0]
0x140086139  mov     [rsp+110h+var_E0], r12
0x14008613e  xor     r9d, r9d
0x140086141  mov     [rsp+110h+var_E8], r12
0x140086146  xor     edx, edx
0x140086148  mov     [rsp+110h+var_F0], r12
0x14008614d  call    CscStoreQueryInformationEntryEx
0x140086152  mov     ebx, eax
0x140086154  test    eax, eax
0x140086156  js      loc_140086381
0x14008615c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086163  cmp     rcx, rsi
0x140086166  jnz     loc_14008638C
0x14008616c  mov     r9d, [rbp+57h+var_A0]
0x140086170  bt      r9d, 17h
0x140086175  jb      loc_1400863B6
0x14008617b  bt      r9d, 10h
0x140086180  jb      loc_1400863B6
0x140086186  lea     rcx, [rbp+57h+var_C8]
0x14008618a  call    CscStoreDereferenceEntry
0x14008618f  mov     rcx, r13
0x140086192  call    cs:__imp_RxQueryNetRootCachingMode
0x140086199  nop     dword ptr [rax+rax+00h]
0x14008619e  cmp     eax, 0FFFFFFFFh
0x1400861a1  jnz     loc_140085FDE
0x1400861a7  test    ebx, ebx
0x1400861a9  js      loc_140085FEE
0x1400861af  mov     ecx, [rbp+57h+var_98]
0x1400861b2  call    CscConvertStoreCacheModeToSmbCacheMode
0x1400861b7  mov     edx, eax
0x1400861b9  mov     rcx, r13
0x1400861bc  call    cs:__imp_RxUpdateNetRootCachingMode
0x1400861c3  nop     dword ptr [rax+rax+00h]
0x1400861c8  jmp     loc_140085FE2
0x1400861cd  mov     ebx, [r15+11Ch]
0x1400861d4  test    ebx, ebx
0x1400861d6  jnz     short loc_1400861DF
0x1400861d8  mov     ebx, [r15+118h]
0x1400861df  mov     ecx, ebx
0x1400861e1  call    CscTransitnOKToGoOffline
0x1400861e6  mov     [rbp+57h+var_D0], ebx
0x1400861e9  mov     sil, al
0x1400861ec  test    al, al
0x1400861ee  jnz     short loc_140086201
0x1400861f0  bt      r14d, 8
0x1400861f5  jb      short loc_14008625C
0x1400861f7  mov     eax, [rdi+64h]
0x1400861fa  test    al, 1
0x1400861fc  jnz     short loc_14008625C
0x1400861fe  xor     sil, sil
0x140086201  mov     rcx, cs:WPP_GLOBAL_Control
0x140086208  lea     rax, WPP_GLOBAL_Control
0x14008620f  cmp     rcx, rax
0x140086212  jnz     loc_1400862A0
0x140086218  test    sil, sil
0x14008621b  jz      loc_140085F2A
0x140086221  mov     rcx, r13
0x140086224  call    cs:__imp_RxQueryNetRootCachingMode
0x14008622b  nop     dword ptr [rax+rax+00h]
0x140086230  cmp     ax, 0Ch
0x140086234  jnz     loc_140085F2A
0x14008623a  mov     rcx, cs:WPP_GLOBAL_Control
0x140086241  lea     rsi, WPP_GLOBAL_Control
0x140086248  cmp     rcx, rsi
0x14008624b  jnz     loc_1400862EB
0x140086251  mov     r14d, 4ECh
0x140086257  jmp     loc_140085FFB
0x14008625c  cmp     ebx, 0C0000022h
0x140086262  jz      short loc_140086298
0x140086264  cmp     ebx, 0C0000064h
0x14008626a  jz      short loc_140086298
0x14008626c  cmp     ebx, 0C000006Ah
0x140086272  jz      short loc_140086298
0x140086274  cmp     ebx, 0C000006Dh
0x14008627a  jz      short loc_140086298
0x14008627c  cmp     ebx, 0C0000071h
0x140086282  jz      short loc_140086298
0x140086284  cmp     ebx, 0C0000224h
0x14008628a  jz      short loc_140086298
0x14008628c  cmp     ebx, 0C0000388h
0x140086292  jnz     loc_1400861FE
0x140086298  mov     sil, 1
0x14008629b  jmp     loc_140086201
0x1400862a0  mov     eax, [rcx+2Ch]
0x1400862a3  test    al, 20h
0x1400862a5  jz      loc_140086218
0x1400862ab  mov     rcx, [rcx+18h]
0x1400862af  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400862b6  mov     al, sil
0x1400862b9  mov     edx, 23h ; '#'
0x1400862be  neg     al
0x1400862c0  mov     eax, [r15+118h]
0x1400862c7  sbb     r9b, r9b
0x1400862ca  mov     dword ptr [rsp+110h+var_E8], eax
0x1400862ce  mov     eax, [r15+11Ch]
0x1400862d5  and     r9b, 0Bh
0x1400862d9  add     r9b, 4Eh ; 'N'
0x1400862dd  mov     dword ptr [rsp+110h+var_F0], eax
0x1400862e1  call    WPP_SF_cDD
0x1400862e6  jmp     loc_140086218
0x1400862eb  mov     eax, [rcx+2Ch]
0x1400862ee  test    al, 20h
0x1400862f0  jz      loc_140086251
0x1400862f6  mov     rcx, [rcx+18h]
0x1400862fa  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140086301  mov     edx, 24h ; '$'
0x140086306  call    WPP_SF_
0x14008630b  jmp     loc_140086251
0x140086310  mov     rcx, [rcx+18h]
0x140086314  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008631b  mov     edx, 25h ; '%'
0x140086320  call    WPP_SF_
0x140086325  jmp     loc_1400860F0
0x14008632a  mov     eax, [rcx+2Ch]
0x14008632d  test    dil, al
0x140086330  jz      short loc_14008634B
0x140086332  mov     r9, [rbp+57h+var_C8]
0x140086336  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008633d  mov     rcx, [rcx+18h]
0x140086341  mov     edx, 27h ; '''
0x140086346  call    WPP_SF_q
0x14008634b  mov     rcx, cs:WPP_GLOBAL_Control
0x140086352  cmp     rcx, rsi
0x140086355  jz      loc_140086131
0x14008635b  mov     eax, [rcx+2Ch]
0x14008635e  test    dil, al
0x140086361  jz      loc_140086131
0x140086367  mov     rcx, [rcx+18h]
0x14008636b  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
  ... truncated ...
```
