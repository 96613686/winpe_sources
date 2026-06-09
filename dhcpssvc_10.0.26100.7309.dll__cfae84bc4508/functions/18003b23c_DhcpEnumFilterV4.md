# DhcpEnumFilterV4

- ea: `0x18003b23c`
- end: `0x18003b797`
- name: `DhcpEnumFilterV4`
- size: `1371`
- prototype: `DWORD __stdcall(WCHAR *ServerIpAddress, LPDHCP_ADDR_PATTERN ResumeHandle, DWORD PreferredMaximum, DHCP_FILTER_LIST_TYPE ListType, LPDHCP_FILTER_ENUM_INFO *EnumFilterInfo, DWORD *ElementsRead, DWORD *ElementsTotal)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180042240`

## callees

- `0x18003b23c`
- `0x1800b36e4`
- `0x1800b4c18`
- `0x1800b4f88`
- `0x1800cc982`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetGetRecordPosition` at `0x18003b381`
- `ESENT!JetGetRecordPosition` at `0x18003b381`
- `ESENT!JetMove` at `0x18003b5ee`
- `ESENT!JetMove` at `0x18003b694`
- `ESENT!JetMove` at `0x18003b5ee`
- `ESENT!JetMove` at `0x18003b694`
- `KERNEL32!LocalAlloc` at `0x18003b3e8`
- `KERNEL32!LocalAlloc` at `0x18003b4e1`
- `KERNEL32!LocalAlloc` at `0x18003b3e8`
- `KERNEL32!LocalAlloc` at `0x18003b4e1`
- `KERNEL32!LocalFree` at `0x18003b457`
- `KERNEL32!LocalFree` at `0x18003b47d`
- `KERNEL32!LocalFree` at `0x18003b493`
- `KERNEL32!LocalFree` at `0x18003b64d`
- `KERNEL32!LocalFree` at `0x18003b66f`
- `KERNEL32!LocalFree` at `0x18003b457`
- `KERNEL32!LocalFree` at `0x18003b47d`
- `KERNEL32!LocalFree` at `0x18003b493`
- `KERNEL32!LocalFree` at `0x18003b64d`
- `KERNEL32!LocalFree` at `0x18003b66f`
- `KERNEL32!EnterCriticalSection` at `0x18003b2bf`
- `KERNEL32!EnterCriticalSection` at `0x18003b2bf`
- `KERNEL32!LeaveCriticalSection` at `0x18003b410`
- `KERNEL32!LeaveCriticalSection` at `0x18003b410`

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
0x18003b23c  push    rbp
0x18003b23e  push    rbx
0x18003b23f  push    rsi
0x18003b240  push    rdi
0x18003b241  push    r12
0x18003b243  push    r13
0x18003b245  push    r14
0x18003b247  push    r15
0x18003b249  lea     rbp, [rsp-0Fh]
0x18003b24e  sub     rsp, 0C8h
0x18003b255  mov     rax, cs:__security_cookie
0x18003b25c  xor     rax, rsp
0x18003b25f  mov     [rbp+47h+var_50], rax
0x18003b263  mov     rax, [rbp+47h+ElementsRead]
0x18003b267  mov     rsi, rcx
0x18003b26a  mov     rcx, [rbp+47h+EnumFilterInfo]
0x18003b26e  mov     ebx, r8d
0x18003b271  mov     dword ptr [rbp+47h+var_B0+4], edx
0x18003b274  xorps   xmm0, xmm0
0x18003b277  xor     edx, edx
0x18003b279  mov     [rbp+47h+var_70], r9
0x18003b27d  mov     [rbp+47h+var_A0], ebx
0x18003b280  mov     r12d, edx
0x18003b283  mov     [rbp+47h+var_68], rcx
0x18003b287  mov     edi, edx
0x18003b289  mov     [rbp+47h+var_A8], rax
0x18003b28d  mov     r15d, edx
0x18003b290  movups  xmmword ptr [rbp+47h+precpos.cbStruct], xmm0
0x18003b294  test    rsi, rsi
0x18003b297  jz      loc_18003B76F
0x18003b29d  test    r9, r9
0x18003b2a0  jz      loc_18003B76F
0x18003b2a6  test    rcx, rcx
0x18003b2a9  jz      loc_18003B76F
0x18003b2af  test    rax, rax
0x18003b2b2  jz      loc_18003B76F
0x18003b2b8  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18003b2bf  call    cs:__imp_EnterCriticalSection
0x18003b2c6  nop     dword ptr [rax+rax+00h]
0x18003b2cb  movzx   eax, byte ptr [rsi+0Ch]
0x18003b2cf  xor     ecx, ecx
0x18003b2d1  mov     r14, cs:FilterGlobalTableHandle
0x18003b2d8  mov     r13, cs:DhcpGlobalJetServerSession
0x18003b2df  mov     [rbp+47h+tableid], r14
0x18003b2e3  mov     byte ptr [rbp+47h+var_B0], bl
0x18003b2e6  test    al, al
0x18003b2e8  jnz     short loc_18003B32E
0x18003b2ea  cmp     [rsi+4], cl
0x18003b2ed  jnz     short loc_18003B32E
0x18003b2ef  cmp     [rsi+8], ecx
0x18003b2f2  jnz     short loc_18003B32E
0x18003b2f4  mov     [rsp+100h+var_B8], ecx; unsigned int
0x18003b2f8  lea     rax, [rbp+47h+var_B0]
0x18003b2fc  mov     [rsp+100h+var_C0], rcx; void *
0x18003b301  lea     r9d, [rdi+1]
0x18003b305  mov     [rsp+100h+cbData], ecx; cbData
0x18003b309  mov     rdx, r14; tableid
0x18003b30c  mov     [rsp+100h+var_D0], rcx; void *
0x18003b311  mov     rcx, r13; sesid
0x18003b314  mov     [rsp+100h+pvData], rax; pvData
0x18003b319  call    FilterJetPrepareSearch
0x18003b31e  mov     ebx, eax
0x18003b320  cmp     eax, 4E2Dh
0x18003b325  jnz     short loc_18003B365
0x18003b327  mov     ebx, 103h
0x18003b32c  jmp     short loc_18003B365
0x18003b32e  mov     [rsp+100h+var_B8], eax; unsigned int
0x18003b332  lea     rcx, [rsi+0Dh]
0x18003b336  mov     [rsp+100h+var_C0], rcx; void *
0x18003b33b  lea     rdx, [rsi+4]
0x18003b33f  mov     [rsp+100h+cbData], 1; cbData
0x18003b347  lea     rax, [rbp+47h+var_B0]
0x18003b34b  mov     [rsp+100h+var_D0], rdx; void *
0x18003b350  xor     r9d, r9d
0x18003b353  mov     rdx, r14; tableid
0x18003b356  mov     [rsp+100h+pvData], rax; pvData
0x18003b35b  mov     rcx, r13; sesid
0x18003b35e  call    FilterJetPrepareSearch
0x18003b363  mov     ebx, eax
0x18003b365  test    ebx, ebx
0x18003b367  jnz     loc_18003B405
0x18003b36d  lea     eax, [rbx+10h]
0x18003b370  mov     rdx, r14; tableid
0x18003b373  mov     r9d, eax; cbRecpos
0x18003b376  mov     [rbp+47h+var_88], rax
0x18003b37a  lea     r8, [rbp+47h+precpos]; precpos
0x18003b37e  mov     rcx, r13; sesid
0x18003b381  call    cs:__imp_JetGetRecordPosition
0x18003b388  nop     dword ptr [rax+rax+00h]
0x18003b38d  mov     ecx, eax
0x18003b38f  lea     rdx, aFilterjetgetcu; "FilterJetGetCurrRecordPosition"
0x18003b396  call    FilterMapJetError
0x18003b39b  mov     ebx, eax
0x18003b39d  test    eax, eax
0x18003b39f  jnz     short loc_18003B405
0x18003b3a1  mov     eax, [rbp+47h+precpos.centriesTotal]
0x18003b3a4  lea     r8d, [rbx+10h]
0x18003b3a8  sub     eax, [rbp+47h+precpos.centriesLT]
0x18003b3ab  mov     ecx, 10000h
0x18003b3b0  cmp     dword ptr [rbp+47h+var_B0+4], ecx
0x18003b3b3  mov     [rbp+47h+var_94], eax
0x18003b3b6  mov     eax, 400h
0x18003b3bb  cmovbe  ecx, dword ptr [rbp+47h+var_B0+4]
0x18003b3bf  cmp     ecx, eax
0x18003b3c1  cmovb   ecx, eax
0x18003b3c4  mov     rax, 0EA0EA0EA0EA0EA0Fh
0x18003b3ce  mov     [rbp+47h+var_9C], ecx
0x18003b3d1  sub     rcx, r8
0x18003b3d4  mul     rcx
0x18003b3d7  lea     ecx, [rbx+40h]; uFlags
0x18003b3da  mov     r14, rdx
0x18003b3dd  mov     edx, r8d; uBytes
0x18003b3e0  shr     r14, 8
0x18003b3e4  mov     [rbp+47h+var_80], r14
0x18003b3e8  call    cs:__imp_LocalAlloc
0x18003b3ef  nop     dword ptr [rax+rax+00h]
0x18003b3f4  mov     r12, rax
0x18003b3f7  test    rax, rax
0x18003b3fa  jnz     loc_18003B4C7
0x18003b400  mov     ebx, 8
0x18003b405  mov     r13, [rbp+47h+var_A8]
0x18003b409  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18003b410  call    cs:__imp_LeaveCriticalSection
0x18003b417  nop     dword ptr [rax+rax+00h]
0x18003b41c  xor     edx, edx
0x18003b41e  test    ebx, ebx
0x18003b420  jz      loc_18003B774
0x18003b426  cmp     ebx, 0EAh
0x18003b42c  jz      loc_18003B774
0x18003b432  cmp     ebx, 103h
0x18003b438  jz      loc_18003B774
0x18003b43e  test    r15d, r15d
0x18003b441  jz      short loc_18003B475
0x18003b443  lea     r14, [rdi+110h]
0x18003b44a  test    rdi, rdi
0x18003b44d  jz      short loc_18003B468
0x18003b44f  mov     rcx, [r14]; hMem
0x18003b452  test    rcx, rcx
0x18003b455  jz      short loc_18003B468
0x18003b457  call    cs:__imp_LocalFree
0x18003b45e  nop     dword ptr [rax+rax+00h]
0x18003b463  xor     edx, edx
0x18003b465  mov     [r14], rdx
0x18003b468  add     r14, 118h
0x18003b46f  sub     r15, 1
0x18003b473  jnz     short loc_18003B44A
0x18003b475  test    rdi, rdi
0x18003b478  jz      short loc_18003B48B
0x18003b47a  mov     rcx, rdi; hMem
0x18003b47d  call    cs:__imp_LocalFree
0x18003b484  nop     dword ptr [rax+rax+00h]
0x18003b489  xor     edx, edx
0x18003b48b  test    r12, r12
0x18003b48e  jz      short loc_18003B4A1
0x18003b490  mov     rcx, r12; hMem
0x18003b493  call    cs:__imp_LocalFree
0x18003b49a  nop     dword ptr [rax+rax+00h]
0x18003b49f  xor     edx, edx
0x18003b4a1  mov     rax, [rbp+47h+var_70]
0x18003b4a5  mov     r8d, 10Ch; Size
0x18003b4ab  mov     rcx, rsi; void *
0x18003b4ae  mov     [rax], rdx
0x18003b4b1  mov     rax, [rbp+47h+var_68]
0x18003b4b5  mov     [rax], edx
0x18003b4b7  mov     [r13+0], edx
0x18003b4bb  xor     edx, edx; Val
0x18003b4bd  call    memset_0
0x18003b4c2  jmp     loc_18003B774
0x18003b4c7  mov     eax, r14d
0x18003b4ca  xorps   xmm0, xmm0
0x18003b4cd  imul    r14, rax, 118h
0x18003b4d4  movups  xmmword ptr [r12], xmm0
0x18003b4d9  mov     ecx, 40h ; '@'; uFlags
0x18003b4de  mov     rdx, r14; uBytes
0x18003b4e1  call    cs:__imp_LocalAlloc
0x18003b4e8  nop     dword ptr [rax+rax+00h]
0x18003b4ed  mov     rdi, rax
0x18003b4f0  test    rax, rax
0x18003b4f3  jz      loc_18003B400
0x18003b4f9  mov     r8, r14; Size
0x18003b4fc  xor     edx, edx; Val
0x18003b4fe  mov     rcx, rax; void *
0x18003b501  call    memset_0
0x18003b506  xor     eax, eax
0x18003b508  mov     r8d, eax
0x18003b50b  mov     dword ptr [rbp+47h+var_B0+4], eax
0x18003b50e  cmp     dword ptr [rbp+47h+var_80], eax
0x18003b511  jbe     loc_18003B6BD
0x18003b517  mov     [rbp+47h+hMem], rax
0x18003b51b  mov     byte ptr [rbp+47h+var_B0], al
0x18003b51e  mov     eax, r15d
0x18003b521  imul    r14, rax, 118h
0x18003b528  mov     [rbp+47h+var_98], r15d
0x18003b52c  add     r14, rdi
0x18003b52f  mov     r9, r14
0x18003b532  lea     rax, [r14+0Ch]
0x18003b536  mov     qword ptr [rsp+100h+cbData], rax; __int64
0x18003b53b  lea     rdx, [r14+4]
0x18003b53f  lea     rax, [rbp+47h+hMem]
0x18003b543  mov     [rsp+100h+var_D0], rax; __int64
0x18003b548  lea     r8, [r14+8]
0x18003b54c  lea     rax, [rbp+47h+var_B0]
0x18003b550  mov     [rsp+100h+var_D8], rax; __int64
0x18003b555  lea     rcx, [r14+0Dh]; void *
0x18003b559  mov     [rsp+100h+pvData], rdx; __int64
0x18003b55e  call    GetFilterTableRecord
0x18003b563  mov     ebx, eax
0x18003b565  test    eax, eax
0x18003b567  jnz     loc_18003B405
0x18003b56d  mov     rdx, [rbp+47h+hMem]
0x18003b571  xor     ebx, ebx
0x18003b573  mov     [r14+110h], rdx
0x18003b57a  test    rdx, rdx
0x18003b57d  jz      short loc_18003B5BD
0x18003b57f  mov     r8d, 80h
0x18003b585  mov     rcx, rdx
0x18003b588  mov     eax, r8d
0x18003b58b  cmp     [rcx], bx
0x18003b58e  jz      short loc_18003B59A
0x18003b590  add     rcx, 2
0x18003b594  sub     rax, 1
0x18003b598  jnz     short loc_18003B58B
0x18003b59a  test    rax, rax
0x18003b59d  jz      loc_18003B62A
0x18003b5a3  mov     rcx, r8
0x18003b5a6  sub     rcx, rax
0x18003b5a9  add     rcx, rcx
0x18003b5ac  neg     rax
0x18003b5af  sbb     rax, rax
0x18003b5b2  and     rcx, rax
0x18003b5b5  add     ecx, 11Ah
0x18003b5bb  jmp     short loc_18003B5C2
0x18003b5bd  mov     ecx, 118h
0x18003b5c2  movzx   eax, byte ptr [rbp+47h+var_B0]
0x18003b5c6  cmp     eax, [rbp+47h+var_A0]
0x18003b5c9  jnz     loc_18003B667
0x18003b5cf  mov     rax, [rbp+47h+var_88]
0x18003b5d3  inc     r15d
0x18003b5d6  add     eax, ecx
0x18003b5d8  cmp     eax, [rbp+47h+var_9C]
0x18003b5db  jnb     short loc_18003B641
0x18003b5dd  mov     rdx, [rbp+47h+tableid]; tableid
0x18003b5e1  xor     r9d, r9d; grbit
0x18003b5e4  mov     rcx, r13; sesid
0x18003b5e7  mov     dword ptr [rbp+47h+var_88], eax
0x18003b5ea  lea     r8d, [r9+1]; cRow
0x18003b5ee  call    cs:__imp_JetMove
0x18003b5f5  nop     dword ptr [rax+rax+00h]
0x18003b5fa  mov     ecx, eax
0x18003b5fc  lea     rdx, aFilterjetgetne; "FilterJetGetNextRecord"
0x18003b603  call    FilterMapJetError
0x18003b608  mov     ebx, eax
0x18003b60a  xor     eax, eax
0x18003b60c  test    ebx, ebx
0x18003b60e  jnz     short loc_18003B634
0x18003b610  mov     r8d, dword ptr [rbp+47h+var_B0+4]
0x18003b614  inc     r8d
0x18003b617  mov     dword ptr [rbp+47h+var_B0+4], r8d
0x18003b61b  cmp     r8d, dword ptr [rbp+47h+var_80]
0x18003b61f  jb      loc_18003B517
0x18003b625  jmp     loc_18003B6BD
0x18003b62a  mov     ebx, 103h
0x18003b62f  jmp     loc_18003B405
0x18003b634  cmp     ebx, 103h
0x18003b63a  jz      short loc_18003B6B9
0x18003b63c  jmp     loc_18003B405
0x18003b641  mov     r15d, [rbp+47h+var_98]
0x18003b645  test    rdx, rdx
0x18003b648  jz      short loc_18003B659
0x18003b64a  mov     rcx, rdx; hMem
0x18003b64d  call    cs:__imp_LocalFree
0x18003b654  nop     dword ptr [rax+rax+00h]
0x18003b659  mov     [r14+110h], rbx
0x18003b660  mov     ebx, 0EAh
0x18003b665  jmp     short loc_18003B6B9
0x18003b667  test    rdx, rdx
0x18003b66a  jz      short loc_18003B686
0x18003b66c  mov     rcx, rdx; hMem
0x18003b66f  call    cs:__imp_LocalFree
0x18003b676  nop     dword ptr [rax+rax+00h]
0x18003b67b  mov     [rbp+47h+hMem], rbx
0x18003b67f  mov     [r14+110h], rbx
0x18003b686  mov     rdx, [rbp+47h+tableid]; tableid
0x18003b68a  xor     r9d, r9d; grbit
0x18003b68d  mov     rcx, r13; sesid
0x18003b690  lea     r8d, [r9+1]; cRow
0x18003b694  call    cs:__imp_JetMove
0x18003b69b  nop     dword ptr [rax+rax+00h]
0x18003b6a0  mov     ecx, eax
0x18003b6a2  lea     rdx, aFilterjetgetne; "FilterJetGetNextRecord"
0x18003b6a9  call    FilterMapJetError
0x18003b6ae  mov     ebx, eax
0x18003b6b0  test    eax, eax
0x18003b6b2  jnz     short loc_18003B634
0x18003b6b4  mov     ebx, 103h
0x18003b6b9  mov     r8d, dword ptr [rbp+47h+var_B0+4]
0x18003b6bd  mov     rax, [rbp+47h+var_70]
0x18003b6c1  mov     rcx, [rbp+47h+var_68]
0x18003b6c5  mov     [r12], r15d
0x18003b6c9  mov     [r12+8], rdi
  ... truncated ...
```
