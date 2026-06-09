# CScrubDatabase::GetParityExtentRecordCount(ulong *)

- ea: `0x18002eddc`
- end: `0x18002f037`
- name: `?GetParityExtentRecordCount@CScrubDatabase@@QEAAJPEAK@Z`
- size: `603`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x1800064d8`
- `0x180006688`
- `0x18002eddc`
- `0x180037620`

## import_xrefs

- `ESENT!JetComputeStats` at `0x18002eeba`
- `ESENT!JetComputeStats` at `0x18002eeba`
- `ESENT!JetGetObjectInfoW` at `0x18002ef64`
- `ESENT!JetGetObjectInfoW` at `0x18002ef64`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::GetParityExtentRecordCount(CScrubDatabase *this, unsigned int *a2)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v5; // rdx
  unsigned int v6; // eax
  int v7; // edi
  unsigned int v8; // ebx
  int v9; // eax
  JET_DBID v10; // edx
  JET_SESID v11; // rcx
  unsigned int ObjectInfoW; // eax
  int v13; // edi
  int v14; // eax
  __int64 v15; // r9
  const char *v17; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-1h]
  _OWORD pvResult[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v20; // [rsp+80h] [rbp+27h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v17 = "CScrubDatabase::GetParityExtentRecordCount";
  v18 = 0;
  v5 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v5 + 16) = "CScrubDatabase::GetParityExtentRecordCount";
  ++*(_WORD *)(v5 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::GetParityExtentRecordCount");
  }
  *a2 = 0;
  v6 = JetComputeStats(*((_QWORD *)this + 1), *((_QWORD *)this + 3));
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v6);
    }
    if ( v7 == -1011 )
    {
      v8 = -2147024882;
    }
    else
    {
      v9 = -v7;
      if ( v7 > 0 )
        LOWORD(v9) = v7;
      v8 = v7 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
    }
  }
  else
  {
    v10 = *((_DWORD *)this + 4);
    v11 = *((_QWORD *)this + 1);
    v20 = 0;
    memset(pvResult, 0, sizeof(pvResult));
    ObjectInfoW = JetGetObjectInfoW(v11, v10, 1u, 0, ParityTable::TableName, pvResult, 0x28u, 0);
    v13 = ObjectInfoW;
    if ( ObjectInfoW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, ObjectInfoW);
      }
      if ( v13 == -1011 )
      {
        v8 = -2147024882;
      }
      else
      {
        v14 = -v13;
        if ( v13 > 0 )
          LOWORD(v14) = v13;
        v8 = v13 & 0x8E5E0000 | (unsigned __int16)v14 | 0xE5E0000;
      }
      v18 = v8;
    }
    else
    {
      v15 = v20;
      *a2 = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids,
          v15,
          HIDWORD(v20));
      }
      v8 = 0;
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v17);
  return v8;
}

```

## disassembly

```asm
0x18002eddc  mov     [rsp-8+arg_10], rbx
0x18002ede1  push    rbp
0x18002ede2  push    rsi
0x18002ede3  push    rdi
0x18002ede4  push    r12
0x18002ede6  push    r14
0x18002ede8  lea     rbp, [rsp-37h]
0x18002eded  sub     rsp, 90h
0x18002edf4  mov     rax, cs:__security_cookie
0x18002edfb  xor     rax, rsp
0x18002edfe  mov     [rbp+57h+var_28], rax
0x18002ee02  mov     rax, gs:58h
0x18002ee0b  lea     r8, aCscrubdatabase_1; "CScrubDatabase::GetParityExtentRecordCo"...
0x18002ee12  mov     rbx, rcx
0x18002ee15  mov     [rbp+57h+var_60], r8
0x18002ee19  mov     ecx, cs:_tls_index
0x18002ee1f  mov     rsi, rdx
0x18002ee22  mov     r14d, 1
0x18002ee28  mov     [rbp+57h+var_58], 0
0x18002ee2f  mov     rdx, [rax+rcx*8]
0x18002ee33  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002ee3a  mov     eax, 10h
0x18002ee3f  mov     [rax+rdx], r8
0x18002ee43  mov     eax, 8
0x18002ee48  add     [rax+rdx], r14w
0x18002ee4d  movzx   edx, word ptr [rax+rdx]
0x18002ee51  movzx   eax, cx
0x18002ee54  cmp     dx, cx
0x18002ee57  cmovb   ax, dx
0x18002ee5b  cmovb   cx, dx
0x18002ee5f  mov     [rbp+57h+var_70], ax
0x18002ee63  xor     eax, eax
0x18002ee65  mov     [rbp+57h+var_6C], eax
0x18002ee68  mov     rax, cs:off_180047060; "                                       "...
0x18002ee6f  mov     [rbp+57h+var_68], rax
0x18002ee73  mov     [rbp+57h+var_6E], cx
0x18002ee77  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee7e  lea     r12, WPP_GLOBAL_Control
0x18002ee85  cmp     rcx, r12
0x18002ee88  jz      short loc_18002EEAC
0x18002ee8a  test    [rcx+1Ch], r14b
0x18002ee8e  jz      short loc_18002EEAC
0x18002ee90  cmp     byte ptr [rcx+19h], 5
0x18002ee94  jb      short loc_18002EEAC
0x18002ee96  mov     rcx, [rcx+10h]; LoggerHandle
0x18002ee9a  lea     edx, [r14+0Ch]
0x18002ee9e  lea     r9, [rbp+57h+var_70]
0x18002eea2  mov     [rsp+0B0h+szObjectName], r8; __int64
0x18002eea7  call    WPP_SF_aZs
0x18002eeac  mov     dword ptr [rsi], 0
0x18002eeb2  mov     rdx, [rbx+18h]; tableid
0x18002eeb6  mov     rcx, [rbx+8]; sesid
0x18002eeba  call    cs:__imp_JetComputeStats
0x18002eec0  mov     edi, eax
0x18002eec2  test    eax, eax
0x18002eec4  jz      short loc_18002EF25
0x18002eec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eecd  cmp     rcx, r12
0x18002eed0  jz      short loc_18002EEF6
0x18002eed2  test    [rcx+1Ch], r14b
0x18002eed6  jz      short loc_18002EEF6
0x18002eed8  cmp     byte ptr [rcx+19h], 2
0x18002eedc  jb      short loc_18002EEF6
0x18002eede  mov     rcx, [rcx+10h]
0x18002eee2  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002eee9  mov     edx, 4Fh ; 'O'
0x18002eeee  mov     r9d, eax
0x18002eef1  call    WPP_SF_d
0x18002eef6  cmp     edi, 0FFFFFC0Dh
0x18002eefc  jnz     short loc_18002EF08
0x18002eefe  mov     ebx, 8007000Eh
0x18002ef03  jmp     loc_18002F009
0x18002ef08  mov     eax, edi
0x18002ef0a  neg     eax
0x18002ef0c  cmovs   eax, edi
0x18002ef0f  and     edi, 8E5E0000h
0x18002ef15  movzx   ebx, ax
0x18002ef18  or      ebx, edi
0x18002ef1a  or      ebx, 0E5E0000h
0x18002ef20  jmp     loc_18002F009
0x18002ef25  mov     edx, [rbx+10h]; dbid
0x18002ef28  xor     eax, eax
0x18002ef2a  mov     rcx, [rbx+8]; sesid
0x18002ef2e  xorps   xmm0, xmm0
0x18002ef31  mov     [rsp+0B0h+InfoLevel], eax; InfoLevel
0x18002ef35  xor     r9d, r9d; szContainerName
0x18002ef38  mov     [rbp+57h+var_30], rax
0x18002ef3c  mov     r8d, r14d; objtyp
0x18002ef3f  lea     rax, [rbp+57h+var_50]
0x18002ef43  mov     [rsp+0B0h+cbMax], 28h ; '('; cbMax
0x18002ef4b  mov     [rsp+0B0h+pvResult], rax; pvResult
0x18002ef50  lea     rax, ?TableName@ParityTable@@3PAGA; "ParityExtent"
0x18002ef57  mov     [rsp+0B0h+szObjectName], rax; szObjectName
0x18002ef5c  movups  [rbp+57h+var_50], xmm0
0x18002ef60  movups  [rbp+57h+var_40], xmm0
0x18002ef64  call    cs:__imp_JetGetObjectInfoW
0x18002ef6a  mov     edi, eax
0x18002ef6c  test    eax, eax
0x18002ef6e  jz      short loc_18002EFCC
0x18002ef70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef77  cmp     rcx, r12
0x18002ef7a  jz      short loc_18002EFA0
0x18002ef7c  test    [rcx+1Ch], r14b
0x18002ef80  jz      short loc_18002EFA0
0x18002ef82  cmp     byte ptr [rcx+19h], 2
0x18002ef86  jb      short loc_18002EFA0
0x18002ef88  mov     rcx, [rcx+10h]
0x18002ef8c  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002ef93  mov     edx, 50h ; 'P'
0x18002ef98  mov     r9d, eax
0x18002ef9b  call    WPP_SF_d
0x18002efa0  cmp     edi, 0FFFFFC0Dh
0x18002efa6  jnz     short loc_18002EFAF
0x18002efa8  mov     ebx, 8007000Eh
0x18002efad  jmp     short loc_18002EFC7
0x18002efaf  mov     eax, edi
0x18002efb1  neg     eax
0x18002efb3  cmovs   eax, edi
0x18002efb6  and     edi, 8E5E0000h
0x18002efbc  movzx   ebx, ax
0x18002efbf  or      ebx, edi
0x18002efc1  or      ebx, 0E5E0000h
0x18002efc7  mov     [rbp+57h+var_58], ebx
0x18002efca  jmp     short loc_18002F009
0x18002efcc  mov     r9, [rbp+57h+var_30]
0x18002efd0  mov     [rsi], r9d
0x18002efd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efda  cmp     rcx, r12
0x18002efdd  jz      short loc_18002F007
0x18002efdf  test    [rcx+1Ch], r14b
0x18002efe3  jz      short loc_18002F007
0x18002efe5  cmp     byte ptr [rcx+19h], 4
0x18002efe9  jb      short loc_18002F007
0x18002efeb  mov     eax, dword ptr [rbp+57h+var_30+4]
0x18002efee  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002eff5  mov     rcx, [rcx+10h]
0x18002eff9  mov     edx, 51h ; 'Q'
0x18002effe  mov     dword ptr [rsp+0B0h+szObjectName], eax
0x18002f002  call    WPP_SF_Dd
0x18002f007  xor     ebx, ebx
0x18002f009  lea     rcx, [rbp+57h+var_60]; this
0x18002f00d  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002f012  mov     eax, ebx
0x18002f014  mov     rcx, [rbp+57h+var_28]
0x18002f018  xor     rcx, rsp; StackCookie
0x18002f01b  call    __security_check_cookie
0x18002f020  mov     rbx, [rsp+0B0h+arg_10]
0x18002f028  add     rsp, 90h
0x18002f02f  pop     r14
0x18002f031  pop     r12
0x18002f033  pop     rdi
0x18002f034  pop     rsi
0x18002f035  pop     rbp
0x18002f036  retn
```
