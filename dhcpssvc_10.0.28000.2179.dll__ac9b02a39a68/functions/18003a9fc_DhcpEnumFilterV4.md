# DhcpEnumFilterV4

- ea: `0x18003a9fc`
- end: `0x18003af53`
- name: `DhcpEnumFilterV4`
- size: `1367`
- prototype: `DWORD __stdcall(WCHAR *ServerIpAddress, LPDHCP_ADDR_PATTERN ResumeHandle, DWORD PreferredMaximum, DHCP_FILTER_LIST_TYPE ListType, LPDHCP_FILTER_ENUM_INFO *EnumFilterInfo, DWORD *ElementsRead, DWORD *ElementsTotal)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180041d40`

## callees

- `0x18003a9fc`
- `0x1800b454c`
- `0x1800b5aac`
- `0x1800b5e24`
- `0x1800cda62`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetGetRecordPosition` at `0x18003ab41`
- `ESENT!JetGetRecordPosition` at `0x18003ab41`
- `ESENT!JetMove` at `0x18003adaa`
- `ESENT!JetMove` at `0x18003ae50`
- `ESENT!JetMove` at `0x18003adaa`
- `ESENT!JetMove` at `0x18003ae50`
- `KERNEL32!LocalAlloc` at `0x18003aba8`
- `KERNEL32!LocalAlloc` at `0x18003aca1`
- `KERNEL32!LocalAlloc` at `0x18003aba8`
- `KERNEL32!LocalAlloc` at `0x18003aca1`
- `KERNEL32!LocalFree` at `0x18003ac17`
- `KERNEL32!LocalFree` at `0x18003ac3d`
- `KERNEL32!LocalFree` at `0x18003ac53`
- `KERNEL32!LocalFree` at `0x18003ae09`
- `KERNEL32!LocalFree` at `0x18003ae2b`
- `KERNEL32!LocalFree` at `0x18003ac17`
- `KERNEL32!LocalFree` at `0x18003ac3d`
- `KERNEL32!LocalFree` at `0x18003ac53`
- `KERNEL32!LocalFree` at `0x18003ae09`
- `KERNEL32!LocalFree` at `0x18003ae2b`
- `KERNEL32!EnterCriticalSection` at `0x18003aa7f`
- `KERNEL32!EnterCriticalSection` at `0x18003aa7f`
- `KERNEL32!LeaveCriticalSection` at `0x18003abd0`
- `KERNEL32!LeaveCriticalSection` at `0x18003abd0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
DWORD __stdcall DhcpEnumFilterV4(
        WCHAR *ServerIpAddress,
        LPDHCP_ADDR_PATTERN ResumeHandle,
        DWORD PreferredMaximum,
        DHCP_FILTER_LIST_TYPE ListType,
        LPDHCP_FILTER_ENUM_INFO *EnumFilterInfo,
        DWORD *ElementsRead,
        DWORD *ElementsTotal)
{
  char v8; // bl
  _QWORD *v9; // r12
  HLOCAL *v10; // rdi
  __int64 v11; // r15
  unsigned int v12; // eax
  JET_TABLEID v13; // r14
  JET_SESID v14; // r13
  DWORD FilterTableRecord; // ebx
  unsigned int RecordPosition; // eax
  __int64 v17; // rcx
  unsigned __int64 v18; // r14
  DWORD *v19; // r13
  HLOCAL *v20; // r14
  size_t v21; // r14
  char *v22; // rax
  unsigned int v23; // r8d
  char *v24; // r14
  _WORD *v25; // rdx
  _WORD *v26; // rcx
  __int64 v27; // rax
  int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // eax
  _QWORD *v31; // rax
  _DWORD *v32; // rcx
  __int64 v33; // rdx
  int v35; // [rsp+28h] [rbp-91h]
  _BYTE pvData[4]; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-65h]
  DWORD *v38; // [rsp+58h] [rbp-61h]
  DWORD v39; // [rsp+60h] [rbp-59h]
  unsigned int v40; // [rsp+64h] [rbp-55h]
  unsigned int v41; // [rsp+68h] [rbp-51h]
  unsigned int v42; // [rsp+6Ch] [rbp-4Dh]
  HLOCAL hMem; // [rsp+70h] [rbp-49h] BYREF
  __int64 v44; // [rsp+78h] [rbp-41h]
  unsigned __int64 v45; // [rsp+80h] [rbp-39h]
  JET_TABLEID tableid; // [rsp+88h] [rbp-31h]
  _QWORD *v47; // [rsp+90h] [rbp-29h]
  LPDHCP_FILTER_ENUM_INFO *v48; // [rsp+98h] [rbp-21h]
  JET_RECPOS precpos; // [rsp+A0h] [rbp-19h] BYREF

  v8 = PreferredMaximum;
  v37 = (unsigned int)ResumeHandle;
  v47 = *(_QWORD **)&ListType;
  v39 = PreferredMaximum;
  v9 = 0;
  v48 = EnumFilterInfo;
  v10 = 0;
  v38 = ElementsRead;
  v11 = 0;
  precpos = 0;
  if ( !ServerIpAddress || !*(_QWORD *)&ListType || !EnumFilterInfo || !ElementsRead )
    return 87;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v12 = *((unsigned __int8 *)ServerIpAddress + 12);
  v13 = FilterGlobalTableHandle;
  v14 = DhcpGlobalJetServerSession;
  tableid = FilterGlobalTableHandle;
  pvData[0] = v8;
  if ( (_BYTE)v12 || *((_BYTE *)ServerIpAddress + 4) || *((_DWORD *)ServerIpAddress + 2) )
  {
    FilterTableRecord = FilterJetPrepareSearch(
                          DhcpGlobalJetServerSession,
                          FilterGlobalTableHandle,
                          pvData,
                          v35,
                          ServerIpAddress + 2,
                          1u,
                          (char *)ServerIpAddress + 13,
                          v12);
  }
  else
  {
    FilterTableRecord = FilterJetPrepareSearch(
                          DhcpGlobalJetServerSession,
                          FilterGlobalTableHandle,
                          pvData,
                          v35,
                          0,
                          0,
                          0,
                          0);
    if ( FilterTableRecord == 20013 )
      FilterTableRecord = 259;
  }
  if ( !FilterTableRecord )
  {
    v44 = 16;
    RecordPosition = JetGetRecordPosition(v14, v13, &precpos, 0x10u);
    FilterTableRecord = FilterMapJetError(RecordPosition, "FilterJetGetCurrRecordPosition");
    if ( !FilterTableRecord )
    {
      v17 = 0x10000;
      v42 = precpos.centriesTotal - precpos.centriesLT;
      if ( v37 <= 0x10000 )
        v17 = v37;
      if ( (unsigned int)v17 < 0x400 )
        v17 = 1024;
      v40 = v17;
      v18 = (v17 - 16) / 0x118uLL;
      v45 = v18;
      v9 = LocalAlloc(0x40u, 0x10u);
      if ( v9
        && (v21 = 280LL * (unsigned int)v18,
            *(_OWORD *)v9 = 0,
            v22 = (char *)LocalAlloc(0x40u, v21),
            (v10 = (HLOCAL *)v22) != 0) )
      {
        memset_0(v22, 0, v21);
        v23 = 0;
        v37 = 0;
        if ( (_DWORD)v45 )
        {
          while ( 1 )
          {
            hMem = 0;
            pvData[0] = 0;
            v41 = v11;
            v24 = (char *)&v10[35 * (unsigned int)v11];
            FilterTableRecord = GetFilterTableRecord(
                                  v24 + 13,
                                  (__int64)(v24 + 4),
                                  (__int64)pvData,
                                  (__int64)&hMem,
                                  (__int64)(v24 + 12));
            if ( FilterTableRecord )
              goto LABEL_19;
            v25 = hMem;
            *((_QWORD *)v24 + 34) = hMem;
            if ( v25 )
            {
              v26 = v25;
              v27 = 128;
              do
              {
                if ( !*v26 )
                  break;
                ++v26;
                --v27;
              }
              while ( v27 );
              if ( !v27 )
                goto LABEL_49;
              v28 = v27 != 0 ? 2 * (128 - v27) + 282 : 282;
            }
            else
            {
              v28 = 280;
            }
            if ( pvData[0] != v39 )
              break;
            v11 = (unsigned int)(v11 + 1);
            if ( v28 + (int)v44 >= v40 )
            {
              v11 = v41;
              if ( v25 )
                LocalFree(v25);
              *((_QWORD *)v24 + 34) = 0;
              FilterTableRecord = 234;
              goto LABEL_59;
            }
            LODWORD(v44) = v28 + v44;
            v29 = JetMove(v14, tableid, 1, 0);
            FilterTableRecord = FilterMapJetError(v29, "FilterJetGetNextRecord");
            if ( FilterTableRecord )
              goto LABEL_50;
            v23 = v37 + 1;
            v37 = v23;
            if ( v23 >= (unsigned int)v45 )
              goto LABEL_60;
          }
          if ( v25 )
          {
            LocalFree(v25);
            hMem = 0;
            *((_QWORD *)v24 + 34) = 0;
          }
          v30 = JetMove(v14, tableid, 1, 0);
          FilterTableRecord = FilterMapJetError(v30, "FilterJetGetNextRecord");
          if ( FilterTableRecord )
          {
LABEL_50:
            if ( FilterTableRecord != 259 )
              goto LABEL_19;
          }
          else
          {
            FilterTableRecord = 259;
          }
LABEL_59:
          v23 = v37;
        }
LABEL_60:
        v31 = v47;
        v32 = v48;
        *(_DWORD *)v9 = v11;
        v9[1] = v10;
        *v31 = v9;
        *v32 = *(_DWORD *)v9;
        if ( (_DWORD)v11 )
        {
          v19 = v38;
          v33 = 35LL * (unsigned int)(v11 - 1);
          if ( FilterTableRecord == 259 )
          {
            *v38 = 0;
            *((_BYTE *)ServerIpAddress + 4) = BYTE4(v10[v33]);
            *((_BYTE *)ServerIpAddress + 12) = BYTE4(v10[v33 + 1]);
            if ( BYTE4(v10[v33 + 1]) )
              memcpy_0((char *)ServerIpAddress + 13, (char *)&v10[v33 + 1] + 5, BYTE4(v10[v33 + 1]));
            FilterTableRecord = 259;
          }
          else
          {
            *v38 = v42 - v23;
            *((_BYTE *)ServerIpAddress + 4) = BYTE4(v10[v33]);
            *((_BYTE *)ServerIpAddress + 12) = BYTE4(v10[v33 + 1]);
            if ( BYTE4(v10[v33 + 1]) )
              memcpy_0((char *)ServerIpAddress + 13, (char *)&v10[v33 + 1] + 5, BYTE4(v10[v33 + 1]));
            FilterTableRecord = 234;
          }
          goto LABEL_20;
        }
LABEL_49:
        FilterTableRecord = 259;
      }
      else
      {
        FilterTableRecord = 8;
      }
    }
  }
LABEL_19:
  v19 = v38;
LABEL_20:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( FilterTableRecord != 234 && FilterTableRecord != 259 )
  {
    if ( (_DWORD)v11 )
    {
      v20 = v10 + 34;
      do
      {
        if ( v10 && *v20 )
        {
          LocalFree(*v20);
          *v20 = 0;
        }
        v20 += 35;
        --v11;
      }
      while ( v11 );
    }
    if ( v10 )
      LocalFree(v10);
    if ( v9 )
      LocalFree(v9);
    *v47 = 0;
    *(_DWORD *)v48 = 0;
    *v19 = 0;
    memset_0(ServerIpAddress, 0, 0x10Cu);
  }
  return FilterTableRecord;
}

```

## disassembly

```asm
0x18003a9fc  push    rbp
0x18003a9fe  push    rbx
0x18003a9ff  push    rsi
0x18003aa00  push    rdi
0x18003aa01  push    r12
0x18003aa03  push    r13
0x18003aa05  push    r14
0x18003aa07  push    r15
0x18003aa09  lea     rbp, [rsp-0Fh]
0x18003aa0e  sub     rsp, 0C8h
0x18003aa15  mov     rax, cs:__security_cookie
0x18003aa1c  xor     rax, rsp
0x18003aa1f  mov     [rbp+47h+var_50], rax
0x18003aa23  mov     rax, [rbp+47h+ElementsRead]
0x18003aa27  mov     rsi, rcx
0x18003aa2a  mov     rcx, [rbp+47h+EnumFilterInfo]
0x18003aa2e  mov     ebx, r8d
0x18003aa31  mov     dword ptr [rbp+47h+var_B0+4], edx
0x18003aa34  xorps   xmm0, xmm0
0x18003aa37  xor     edx, edx
0x18003aa39  mov     [rbp+47h+var_70], r9
0x18003aa3d  mov     [rbp+47h+var_A0], ebx
0x18003aa40  mov     r12d, edx
0x18003aa43  mov     [rbp+47h+var_68], rcx
0x18003aa47  mov     edi, edx
0x18003aa49  mov     [rbp+47h+var_A8], rax
0x18003aa4d  mov     r15d, edx
0x18003aa50  movups  xmmword ptr [rbp+47h+precpos.cbStruct], xmm0
0x18003aa54  test    rsi, rsi
0x18003aa57  jz      loc_18003AF2B
0x18003aa5d  test    r9, r9
0x18003aa60  jz      loc_18003AF2B
0x18003aa66  test    rcx, rcx
0x18003aa69  jz      loc_18003AF2B
0x18003aa6f  test    rax, rax
0x18003aa72  jz      loc_18003AF2B
0x18003aa78  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18003aa7f  call    cs:__imp_EnterCriticalSection
0x18003aa86  nop     dword ptr [rax+rax+00h]
0x18003aa8b  movzx   eax, byte ptr [rsi+0Ch]
0x18003aa8f  xor     ecx, ecx
0x18003aa91  mov     r14, cs:FilterGlobalTableHandle
0x18003aa98  mov     r13, cs:DhcpGlobalJetServerSession
0x18003aa9f  mov     [rbp+47h+tableid], r14
0x18003aaa3  mov     byte ptr [rbp+47h+var_B0], bl
0x18003aaa6  test    al, al
0x18003aaa8  jnz     short loc_18003AAEE
0x18003aaaa  cmp     [rsi+4], cl
0x18003aaad  jnz     short loc_18003AAEE
0x18003aaaf  cmp     [rsi+8], ecx
0x18003aab2  jnz     short loc_18003AAEE
0x18003aab4  mov     [rsp+100h+var_B8], ecx; unsigned int
0x18003aab8  lea     rax, [rbp+47h+var_B0]
0x18003aabc  mov     [rsp+100h+var_C0], rcx; void *
0x18003aac1  lea     r9d, [rdi+1]
0x18003aac5  mov     [rsp+100h+cbData], ecx; cbData
0x18003aac9  mov     rdx, r14; tableid
0x18003aacc  mov     [rsp+100h+var_D0], rcx; void *
0x18003aad1  mov     rcx, r13; sesid
0x18003aad4  mov     [rsp+100h+pvData], rax; pvData
0x18003aad9  call    FilterJetPrepareSearch
0x18003aade  mov     ebx, eax
0x18003aae0  cmp     eax, 4E2Dh
0x18003aae5  jnz     short loc_18003AB25
0x18003aae7  mov     ebx, 103h
0x18003aaec  jmp     short loc_18003AB25
0x18003aaee  mov     [rsp+100h+var_B8], eax; unsigned int
0x18003aaf2  lea     rcx, [rsi+0Dh]
0x18003aaf6  mov     [rsp+100h+var_C0], rcx; void *
0x18003aafb  lea     rdx, [rsi+4]
0x18003aaff  mov     [rsp+100h+cbData], 1; cbData
0x18003ab07  lea     rax, [rbp+47h+var_B0]
0x18003ab0b  mov     [rsp+100h+var_D0], rdx; void *
0x18003ab10  xor     r9d, r9d
0x18003ab13  mov     rdx, r14; tableid
0x18003ab16  mov     [rsp+100h+pvData], rax; pvData
0x18003ab1b  mov     rcx, r13; sesid
0x18003ab1e  call    FilterJetPrepareSearch
0x18003ab23  mov     ebx, eax
0x18003ab25  test    ebx, ebx
0x18003ab27  jnz     loc_18003ABC5
0x18003ab2d  lea     eax, [rbx+10h]
0x18003ab30  mov     rdx, r14; tableid
0x18003ab33  mov     r9d, eax; cbRecpos
0x18003ab36  mov     [rbp+47h+var_88], rax
0x18003ab3a  lea     r8, [rbp+47h+precpos]; precpos
0x18003ab3e  mov     rcx, r13; sesid
0x18003ab41  call    cs:__imp_JetGetRecordPosition
0x18003ab48  nop     dword ptr [rax+rax+00h]
0x18003ab4d  mov     ecx, eax
0x18003ab4f  lea     rdx, aFilterjetgetcu; "FilterJetGetCurrRecordPosition"
0x18003ab56  call    FilterMapJetError
0x18003ab5b  mov     ebx, eax
0x18003ab5d  test    eax, eax
0x18003ab5f  jnz     short loc_18003ABC5
0x18003ab61  mov     eax, [rbp+47h+precpos.centriesTotal]
0x18003ab64  lea     r8d, [rbx+10h]
0x18003ab68  sub     eax, [rbp+47h+precpos.centriesLT]
0x18003ab6b  mov     ecx, 10000h
0x18003ab70  cmp     dword ptr [rbp+47h+var_B0+4], ecx
0x18003ab73  mov     [rbp+47h+var_94], eax
0x18003ab76  mov     eax, 400h
0x18003ab7b  cmovbe  ecx, dword ptr [rbp+47h+var_B0+4]
0x18003ab7f  cmp     ecx, eax
0x18003ab81  cmovb   ecx, eax
0x18003ab84  mov     rax, 0EA0EA0EA0EA0EA0Fh
0x18003ab8e  mov     [rbp+47h+var_9C], ecx
0x18003ab91  sub     rcx, r8
0x18003ab94  mul     rcx
0x18003ab97  lea     ecx, [rbx+40h]; uFlags
0x18003ab9a  mov     r14, rdx
0x18003ab9d  mov     edx, r8d; uBytes
0x18003aba0  shr     r14, 8
0x18003aba4  mov     [rbp+47h+var_80], r14
0x18003aba8  call    cs:__imp_LocalAlloc
0x18003abaf  nop     dword ptr [rax+rax+00h]
0x18003abb4  mov     r12, rax
0x18003abb7  test    rax, rax
0x18003abba  jnz     loc_18003AC87
0x18003abc0  mov     ebx, 8
0x18003abc5  mov     r13, [rbp+47h+var_A8]
0x18003abc9  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18003abd0  call    cs:__imp_LeaveCriticalSection
0x18003abd7  nop     dword ptr [rax+rax+00h]
0x18003abdc  xor     edx, edx
0x18003abde  test    ebx, ebx
0x18003abe0  jz      loc_18003AF30
0x18003abe6  cmp     ebx, 0EAh
0x18003abec  jz      loc_18003AF30
0x18003abf2  cmp     ebx, 103h
0x18003abf8  jz      loc_18003AF30
0x18003abfe  test    r15d, r15d
0x18003ac01  jz      short loc_18003AC35
0x18003ac03  lea     r14, [rdi+110h]
0x18003ac0a  test    rdi, rdi
0x18003ac0d  jz      short loc_18003AC28
0x18003ac0f  mov     rcx, [r14]; hMem
0x18003ac12  test    rcx, rcx
0x18003ac15  jz      short loc_18003AC28
0x18003ac17  call    cs:__imp_LocalFree
0x18003ac1e  nop     dword ptr [rax+rax+00h]
0x18003ac23  xor     edx, edx
0x18003ac25  mov     [r14], rdx
0x18003ac28  add     r14, 118h
0x18003ac2f  sub     r15, 1
0x18003ac33  jnz     short loc_18003AC0A
0x18003ac35  test    rdi, rdi
0x18003ac38  jz      short loc_18003AC4B
0x18003ac3a  mov     rcx, rdi; hMem
0x18003ac3d  call    cs:__imp_LocalFree
0x18003ac44  nop     dword ptr [rax+rax+00h]
0x18003ac49  xor     edx, edx
0x18003ac4b  test    r12, r12
0x18003ac4e  jz      short loc_18003AC61
0x18003ac50  mov     rcx, r12; hMem
0x18003ac53  call    cs:__imp_LocalFree
0x18003ac5a  nop     dword ptr [rax+rax+00h]
0x18003ac5f  xor     edx, edx
0x18003ac61  mov     rax, [rbp+47h+var_70]
0x18003ac65  mov     r8d, 10Ch; Size
0x18003ac6b  mov     rcx, rsi; void *
0x18003ac6e  mov     [rax], rdx
0x18003ac71  mov     rax, [rbp+47h+var_68]
0x18003ac75  mov     [rax], edx
0x18003ac77  mov     [r13+0], edx
0x18003ac7b  xor     edx, edx; Val
0x18003ac7d  call    memset_0
0x18003ac82  jmp     loc_18003AF30
0x18003ac87  mov     eax, r14d
0x18003ac8a  xorps   xmm0, xmm0
0x18003ac8d  imul    r14, rax, 118h
0x18003ac94  movups  xmmword ptr [r12], xmm0
0x18003ac99  mov     ecx, 40h ; '@'; uFlags
0x18003ac9e  mov     rdx, r14; uBytes
0x18003aca1  call    cs:__imp_LocalAlloc
0x18003aca8  nop     dword ptr [rax+rax+00h]
0x18003acad  mov     rdi, rax
0x18003acb0  test    rax, rax
0x18003acb3  jz      loc_18003ABC0
0x18003acb9  mov     r8, r14; Size
0x18003acbc  xor     edx, edx; Val
0x18003acbe  mov     rcx, rax; void *
0x18003acc1  call    memset_0
0x18003acc6  xor     eax, eax
0x18003acc8  mov     r8d, eax
0x18003accb  mov     dword ptr [rbp+47h+var_B0+4], eax
0x18003acce  cmp     dword ptr [rbp+47h+var_80], eax
0x18003acd1  jbe     loc_18003AE79
0x18003acd7  mov     [rbp+47h+hMem], rax
0x18003acdb  mov     byte ptr [rbp+47h+var_B0], al
0x18003acde  mov     eax, r15d
0x18003ace1  imul    r14, rax, 118h
0x18003ace8  mov     [rbp+47h+var_98], r15d
0x18003acec  add     r14, rdi
0x18003acef  mov     r9, r14
0x18003acf2  lea     rax, [r14+0Ch]
0x18003acf6  mov     qword ptr [rsp+100h+cbData], rax; __int64
0x18003acfb  lea     rdx, [r14+4]
0x18003acff  lea     rax, [rbp+47h+hMem]
0x18003ad03  mov     [rsp+100h+var_D0], rax; __int64
0x18003ad08  lea     r8, [r14+8]
0x18003ad0c  lea     rax, [rbp+47h+var_B0]
0x18003ad10  mov     [rsp+100h+var_D8], rax; __int64
0x18003ad15  lea     rcx, [r14+0Dh]; void *
0x18003ad19  mov     [rsp+100h+pvData], rdx; __int64
0x18003ad1e  call    GetFilterTableRecord
0x18003ad23  mov     ebx, eax
0x18003ad25  test    eax, eax
0x18003ad27  jnz     loc_18003ABC5
0x18003ad2d  mov     rdx, [rbp+47h+hMem]
0x18003ad31  xor     ebx, ebx
0x18003ad33  mov     [r14+110h], rdx
0x18003ad3a  test    rdx, rdx
0x18003ad3d  jz      short loc_18003AD79
0x18003ad3f  mov     r8d, 80h
0x18003ad45  mov     rcx, rdx
0x18003ad48  mov     eax, r8d
0x18003ad4b  cmp     [rcx], bx
0x18003ad4e  jz      short loc_18003AD5A
0x18003ad50  add     rcx, 2
0x18003ad54  sub     rax, 1
0x18003ad58  jnz     short loc_18003AD4B
0x18003ad5a  test    rax, rax
0x18003ad5d  jz      loc_18003ADE6
0x18003ad63  mov     ecx, r8d
0x18003ad66  sub     ecx, eax
0x18003ad68  add     ecx, ecx
0x18003ad6a  neg     rax
0x18003ad6d  sbb     eax, eax
0x18003ad6f  and     ecx, eax
0x18003ad71  add     ecx, 11Ah
0x18003ad77  jmp     short loc_18003AD7E
0x18003ad79  mov     ecx, 118h
0x18003ad7e  movzx   eax, byte ptr [rbp+47h+var_B0]
0x18003ad82  cmp     eax, [rbp+47h+var_A0]
0x18003ad85  jnz     loc_18003AE23
0x18003ad8b  mov     rax, [rbp+47h+var_88]
0x18003ad8f  inc     r15d
0x18003ad92  add     eax, ecx
0x18003ad94  cmp     eax, [rbp+47h+var_9C]
0x18003ad97  jnb     short loc_18003ADFD
0x18003ad99  mov     rdx, [rbp+47h+tableid]; tableid
0x18003ad9d  xor     r9d, r9d; grbit
0x18003ada0  mov     rcx, r13; sesid
0x18003ada3  mov     dword ptr [rbp+47h+var_88], eax
0x18003ada6  lea     r8d, [r9+1]; cRow
0x18003adaa  call    cs:__imp_JetMove
0x18003adb1  nop     dword ptr [rax+rax+00h]
0x18003adb6  mov     ecx, eax
0x18003adb8  lea     rdx, aFilterjetgetne; "FilterJetGetNextRecord"
0x18003adbf  call    FilterMapJetError
0x18003adc4  mov     ebx, eax
0x18003adc6  xor     eax, eax
0x18003adc8  test    ebx, ebx
0x18003adca  jnz     short loc_18003ADF0
0x18003adcc  mov     r8d, dword ptr [rbp+47h+var_B0+4]
0x18003add0  inc     r8d
0x18003add3  mov     dword ptr [rbp+47h+var_B0+4], r8d
0x18003add7  cmp     r8d, dword ptr [rbp+47h+var_80]
0x18003addb  jb      loc_18003ACD7
0x18003ade1  jmp     loc_18003AE79
0x18003ade6  mov     ebx, 103h
0x18003adeb  jmp     loc_18003ABC5
0x18003adf0  cmp     ebx, 103h
0x18003adf6  jz      short loc_18003AE75
0x18003adf8  jmp     loc_18003ABC5
0x18003adfd  mov     r15d, [rbp+47h+var_98]
0x18003ae01  test    rdx, rdx
0x18003ae04  jz      short loc_18003AE15
0x18003ae06  mov     rcx, rdx; hMem
0x18003ae09  call    cs:__imp_LocalFree
0x18003ae10  nop     dword ptr [rax+rax+00h]
0x18003ae15  mov     [r14+110h], rbx
0x18003ae1c  mov     ebx, 0EAh
0x18003ae21  jmp     short loc_18003AE75
0x18003ae23  test    rdx, rdx
0x18003ae26  jz      short loc_18003AE42
0x18003ae28  mov     rcx, rdx; hMem
0x18003ae2b  call    cs:__imp_LocalFree
0x18003ae32  nop     dword ptr [rax+rax+00h]
0x18003ae37  mov     [rbp+47h+hMem], rbx
0x18003ae3b  mov     [r14+110h], rbx
0x18003ae42  mov     rdx, [rbp+47h+tableid]; tableid
0x18003ae46  xor     r9d, r9d; grbit
0x18003ae49  mov     rcx, r13; sesid
0x18003ae4c  lea     r8d, [r9+1]; cRow
0x18003ae50  call    cs:__imp_JetMove
0x18003ae57  nop     dword ptr [rax+rax+00h]
0x18003ae5c  mov     ecx, eax
0x18003ae5e  lea     rdx, aFilterjetgetne; "FilterJetGetNextRecord"
0x18003ae65  call    FilterMapJetError
0x18003ae6a  mov     ebx, eax
0x18003ae6c  test    eax, eax
0x18003ae6e  jnz     short loc_18003ADF0
0x18003ae70  mov     ebx, 103h
0x18003ae75  mov     r8d, dword ptr [rbp+47h+var_B0+4]
0x18003ae79  mov     rax, [rbp+47h+var_70]
0x18003ae7d  mov     rcx, [rbp+47h+var_68]
0x18003ae81  mov     [r12], r15d
0x18003ae85  mov     [r12+8], rdi
  ... truncated ...
```
