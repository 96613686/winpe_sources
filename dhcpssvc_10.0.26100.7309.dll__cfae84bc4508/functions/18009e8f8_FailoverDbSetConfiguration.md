# FailoverDbSetConfiguration

- ea: `0x18009e8f8`
- end: `0x18009ed7d`
- name: `FailoverDbSetConfiguration`
- size: `1157`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009d1a0`

## callees

- `0x18000323c`
- `0x18009e8f8`
- `0x18009f738`
- `0x18009f790`
- `0x18009fe78`
- `0x18009fea4`
- `0x18009fee0`

## import_xrefs

- `msvcrt!time` at `0x18009ecc4`
- `msvcrt!time` at `0x18009ecc4`
- `ESENT!JetCommitTransaction` at `0x18009ed30`
- `ESENT!JetCommitTransaction` at `0x18009ed30`
- `KERNEL32!HeapAlloc` at `0x18009ec27`
- `KERNEL32!HeapAlloc` at `0x18009ec27`
- `KERNEL32!HeapFree` at `0x18009ed17`
- `KERNEL32!HeapFree` at `0x18009ed17`

## string_xrefs

- `0x18009ed3e`: `DhcpDALJetCommitTransaction`

## pseudocode

```c
__int64 __fastcall FailoverDbSetConfiguration(JET_SESID sesid, _QWORD *a2)
{
  _WORD *v4; // rax
  __int64 v6; // rcx
  __int64 v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // r9
  unsigned int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rax
  _WORD *v13; // rcx
  unsigned int v14; // eax
  bool v15; // cf
  __int64 v16; // r9
  _WORD *v17; // rcx
  unsigned int v18; // eax
  _DWORD *v19; // rax
  unsigned __int64 v20; // rax
  unsigned int v21; // ebp
  _DWORD *v22; // r14
  __int64 v23; // rax
  unsigned int i; // r8d
  __int64 v25; // rdx
  unsigned int v26; // eax
  int v27; // [rsp+70h] [rbp+18h] BYREF

  v27 = 0;
  v4 = (_WORD *)a2[4];
  if ( !v4 )
    return 87;
  v6 = 2147483646;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v6;
  }
  while ( v6 );
  if ( !v6 )
  {
    v15 = 0;
    return v15 ? 0 : 0x57;
  }
  v7 = (2 * (2147483646 - v6)) & -(__int64)(v6 != 0);
  v8 = DhcpDALJetBeginTransaction(sesid);
  if ( v8 )
    goto LABEL_44;
  v9 = a2[4];
  v10 = 0;
  if ( v9 )
    v10 = v7 + 2;
  v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7268, v9, v10);
  if ( v8 )
    goto LABEL_44;
  v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F72E0, (int)a2 + 12, 4u);
  if ( v8 )
    goto LABEL_44;
  v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7358, (int)a2 + 24, 4u);
  if ( v8 )
    goto LABEL_44;
  v11 = a2[5];
  if ( !v11 )
  {
    v14 = 0;
LABEL_21:
    v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7298, v11, v14);
    if ( v8 )
      goto LABEL_44;
    v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7280, (_DWORD)a2, 4u);
    if ( v8 )
      goto LABEL_44;
    v16 = a2[6];
    if ( !v16 )
    {
      v18 = 0;
      goto LABEL_30;
    }
    v12 = 2147483646;
    v17 = (_WORD *)a2[6];
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v12;
    }
    while ( v12 );
    if ( v12 )
    {
      v18 = v12 != 0 ? 2 * (2147483646 - v12) + 2 : 2;
LABEL_30:
      v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F72C8, v16, v18);
      if ( !v8 )
      {
        v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F72B0, (int)a2 + 4, 4u);
        if ( !v8 )
        {
          v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7370, (int)a2 + 28, 4u);
          if ( !v8 )
          {
            v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F72F8, (int)a2 + 8, 4u);
            if ( !v8 )
            {
              v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7310, (int)a2 + 64, 1u);
              if ( !v8 )
              {
                v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7328, (int)a2 + 16, 4u);
                if ( !v8 )
                {
                  v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7340, (int)a2 + 20, 4u);
                  if ( !v8 )
                  {
                    v19 = (_DWORD *)a2[7];
                    if ( !v19 || !*v19 )
                      goto LABEL_52;
                    v20 = 4LL * (unsigned int)*v19;
                    if ( v20 <= 0xFFFFFFFF )
                    {
                      v8 = 8;
                      v21 = v20;
                      v22 = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v20);
                      if ( !v22 )
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                        {
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            11,
                            &WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids);
                        }
                        goto LABEL_44;
                      }
                      v23 = a2[7];
                      for ( i = 0; i < *(_DWORD *)v23; v23 = a2[7] )
                      {
                        v25 = i++;
                        v22[v25] = *(_DWORD *)(*(_QWORD *)(v23 + 8) + 4 * v25);
                      }
                      v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7388, (_DWORD)v22, v21);
                      if ( !v8 )
                      {
                        v27 = time(0);
                        v8 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F73A0, (unsigned int)&v27, 4u);
                        if ( !v8 )
                          v8 = DhcpDALJetCommitUpdate(sesid, FailoverConfTableHandle);
                      }
                      HeapFree(gDhcpHeap, 0, v22);
                      if ( v8 )
                        goto LABEL_44;
LABEL_52:
                      v26 = JetCommitTransaction(sesid, 0);
                      return (unsigned int)DhcpDALMapJetError(v26, "DhcpDALJetCommitTransaction");
                    }
                    v8 = 534;
                  }
                }
              }
            }
          }
        }
      }
LABEL_44:
      DhcpDALJetRollback(sesid);
      return v8;
    }
    goto LABEL_19;
  }
  v12 = 2147483646;
  v13 = (_WORD *)a2[5];
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  if ( v12 )
  {
    v14 = v12 != 0 ? 2 * (2147483646 - v12) + 2 : 2;
    goto LABEL_21;
  }
LABEL_19:
  v15 = v12 != 0;
  return v15 ? 0 : 0x57;
}

```

## disassembly

```asm
0x18009e8f8  mov     rax, rsp
0x18009e8fb  mov     [rax+8], rbx
0x18009e8ff  mov     [rax+10h], rbp
0x18009e903  mov     [rax+18h], r8d
0x18009e907  push    rsi
0x18009e908  push    rdi
0x18009e909  push    r12
0x18009e90b  push    r14
0x18009e90d  push    r15
0x18009e90f  sub     rsp, 30h
0x18009e913  xor     r15d, r15d
0x18009e916  mov     rsi, rdx
0x18009e919  mov     [rax+18h], r15d
0x18009e91d  mov     rdi, rcx
0x18009e920  mov     rax, [rdx+20h]
0x18009e924  test    rax, rax
0x18009e927  jnz     short loc_18009E932
0x18009e929  lea     eax, [r15+57h]
0x18009e92d  jmp     loc_18009ED65
0x18009e932  mov     ebp, 7FFFFFFEh
0x18009e937  mov     ecx, ebp
0x18009e939  cmp     [rax], r15w
0x18009e93d  jz      short loc_18009E949
0x18009e93f  add     rax, 2
0x18009e943  sub     rcx, 1
0x18009e947  jnz     short loc_18009E939
0x18009e949  test    rcx, rcx
0x18009e94c  jz      loc_18009ED5B
0x18009e952  mov     rax, rbp
0x18009e955  sub     rax, rcx
0x18009e958  add     rax, rax
0x18009e95b  neg     rcx
0x18009e95e  mov     rcx, rdi
0x18009e961  sbb     r14, r14
0x18009e964  and     r14, rax
0x18009e967  call    DhcpDALJetBeginTransaction
0x18009e96c  mov     ebx, eax
0x18009e96e  test    eax, eax
0x18009e970  jnz     loc_18009EC6A
0x18009e976  mov     r9, [rsi+20h]
0x18009e97a  mov     eax, r15d
0x18009e97d  test    r9, r9
0x18009e980  jz      short loc_18009E986
0x18009e982  lea     eax, [r14+2]
0x18009e986  mov     r8d, cs:dword_1800F7268
0x18009e98d  mov     rcx, rdi
0x18009e990  mov     rdx, cs:FailoverConfTableHandle
0x18009e997  mov     [rsp+58h+var_38], eax
0x18009e99b  call    DhcpDALJetSetValue
0x18009e9a0  mov     ebx, eax
0x18009e9a2  test    eax, eax
0x18009e9a4  jnz     loc_18009EC6A
0x18009e9aa  mov     r8d, cs:dword_1800F72E0
0x18009e9b1  lea     r12d, [rax+4]
0x18009e9b5  mov     rdx, cs:FailoverConfTableHandle
0x18009e9bc  lea     r9, [rsi+0Ch]
0x18009e9c0  mov     rcx, rdi
0x18009e9c3  mov     [rsp+58h+var_38], r12d
0x18009e9c8  call    DhcpDALJetSetValue
0x18009e9cd  mov     ebx, eax
0x18009e9cf  test    eax, eax
0x18009e9d1  jnz     loc_18009EC6A
0x18009e9d7  mov     r8d, cs:dword_1800F7358
0x18009e9de  lea     r9, [rsi+18h]
0x18009e9e2  mov     rdx, cs:FailoverConfTableHandle
0x18009e9e9  mov     rcx, rdi
0x18009e9ec  mov     [rsp+58h+var_38], r12d
0x18009e9f1  call    DhcpDALJetSetValue
0x18009e9f6  mov     ebx, eax
0x18009e9f8  test    eax, eax
0x18009e9fa  jnz     loc_18009EC6A
0x18009ea00  mov     r9, [rsi+28h]
0x18009ea04  test    r9, r9
0x18009ea07  jz      short loc_18009EA43
0x18009ea09  mov     rax, rbp
0x18009ea0c  mov     rcx, r9
0x18009ea0f  cmp     [rcx], r15w
0x18009ea13  jz      short loc_18009EA1F
0x18009ea15  add     rcx, 2
0x18009ea19  sub     rax, 1
0x18009ea1d  jnz     short loc_18009EA0F
0x18009ea1f  test    rax, rax
0x18009ea22  jz      short loc_18009EA3B
0x18009ea24  mov     rcx, rbp
0x18009ea27  sub     rcx, rax
0x18009ea2a  add     rcx, rcx
0x18009ea2d  neg     rax
0x18009ea30  sbb     rax, rax
0x18009ea33  and     rax, rcx
0x18009ea36  add     eax, 2
0x18009ea39  jmp     short loc_18009EA46
0x18009ea3b  neg     rax
0x18009ea3e  jmp     loc_18009ED5E
0x18009ea43  mov     eax, r15d
0x18009ea46  mov     r8d, cs:dword_1800F7298
0x18009ea4d  mov     rcx, rdi
0x18009ea50  mov     rdx, cs:FailoverConfTableHandle
0x18009ea57  mov     [rsp+58h+var_38], eax
0x18009ea5b  call    DhcpDALJetSetValue
0x18009ea60  mov     ebx, eax
0x18009ea62  test    eax, eax
0x18009ea64  jnz     loc_18009EC6A
0x18009ea6a  mov     r8d, cs:dword_1800F7280
0x18009ea71  mov     r9, rsi
0x18009ea74  mov     rdx, cs:FailoverConfTableHandle
0x18009ea7b  mov     rcx, rdi
0x18009ea7e  mov     [rsp+58h+var_38], r12d
0x18009ea83  call    DhcpDALJetSetValue
0x18009ea88  mov     ebx, eax
0x18009ea8a  test    eax, eax
0x18009ea8c  jnz     loc_18009EC6A
0x18009ea92  mov     r9, [rsi+30h]
0x18009ea96  test    r9, r9
0x18009ea99  jz      short loc_18009EACA
0x18009ea9b  mov     rax, rbp
0x18009ea9e  mov     rcx, r9
0x18009eaa1  cmp     [rcx], r15w
0x18009eaa5  jz      short loc_18009EAB1
0x18009eaa7  add     rcx, 2
0x18009eaab  sub     rax, 1
0x18009eaaf  jnz     short loc_18009EAA1
0x18009eab1  test    rax, rax
0x18009eab4  jz      short loc_18009EA3B
0x18009eab6  sub     rbp, rax
0x18009eab9  add     rbp, rbp
0x18009eabc  neg     rax
0x18009eabf  sbb     rax, rax
0x18009eac2  and     rax, rbp
0x18009eac5  add     eax, 2
0x18009eac8  jmp     short loc_18009EACD
0x18009eaca  mov     eax, r15d
0x18009eacd  mov     r8d, cs:dword_1800F72C8
0x18009ead4  mov     rcx, rdi
0x18009ead7  mov     rdx, cs:FailoverConfTableHandle
0x18009eade  mov     [rsp+58h+var_38], eax
0x18009eae2  call    DhcpDALJetSetValue
0x18009eae7  mov     ebx, eax
0x18009eae9  test    eax, eax
0x18009eaeb  jnz     loc_18009EC6A
0x18009eaf1  mov     r8d, cs:dword_1800F72B0
0x18009eaf8  lea     r9, [rsi+4]
0x18009eafc  mov     rdx, cs:FailoverConfTableHandle
0x18009eb03  mov     rcx, rdi
0x18009eb06  mov     [rsp+58h+var_38], r12d
0x18009eb0b  call    DhcpDALJetSetValue
0x18009eb10  mov     ebx, eax
0x18009eb12  test    eax, eax
0x18009eb14  jnz     loc_18009EC6A
0x18009eb1a  mov     r8d, cs:dword_1800F7370
0x18009eb21  lea     r9, [rsi+1Ch]
0x18009eb25  mov     rdx, cs:FailoverConfTableHandle
0x18009eb2c  mov     rcx, rdi
0x18009eb2f  mov     [rsp+58h+var_38], r12d
0x18009eb34  call    DhcpDALJetSetValue
0x18009eb39  mov     ebx, eax
0x18009eb3b  test    eax, eax
0x18009eb3d  jnz     loc_18009EC6A
0x18009eb43  mov     r8d, cs:dword_1800F72F8
0x18009eb4a  lea     r9, [rsi+8]
0x18009eb4e  mov     rdx, cs:FailoverConfTableHandle
0x18009eb55  mov     rcx, rdi
0x18009eb58  mov     [rsp+58h+var_38], r12d
0x18009eb5d  call    DhcpDALJetSetValue
0x18009eb62  mov     ebx, eax
0x18009eb64  test    eax, eax
0x18009eb66  jnz     loc_18009EC6A
0x18009eb6c  mov     r8d, cs:dword_1800F7310
0x18009eb73  lea     r9, [rsi+40h]
0x18009eb77  mov     rdx, cs:FailoverConfTableHandle
0x18009eb7e  mov     rcx, rdi
0x18009eb81  mov     [rsp+58h+var_38], 1
0x18009eb89  call    DhcpDALJetSetValue
0x18009eb8e  mov     ebx, eax
0x18009eb90  test    eax, eax
0x18009eb92  jnz     loc_18009EC6A
0x18009eb98  mov     r8d, cs:dword_1800F7328
0x18009eb9f  lea     r9, [rsi+10h]
0x18009eba3  mov     rdx, cs:FailoverConfTableHandle
0x18009ebaa  mov     rcx, rdi
0x18009ebad  mov     [rsp+58h+var_38], r12d
0x18009ebb2  call    DhcpDALJetSetValue
0x18009ebb7  mov     ebx, eax
0x18009ebb9  test    eax, eax
0x18009ebbb  jnz     loc_18009EC6A
0x18009ebc1  mov     r8d, cs:dword_1800F7340
0x18009ebc8  lea     r9, [rsi+14h]
0x18009ebcc  mov     rdx, cs:FailoverConfTableHandle
0x18009ebd3  mov     rcx, rdi
0x18009ebd6  mov     [rsp+58h+var_38], r12d
0x18009ebdb  call    DhcpDALJetSetValue
0x18009ebe0  mov     ebx, eax
0x18009ebe2  test    eax, eax
0x18009ebe4  jnz     loc_18009EC6A
0x18009ebea  mov     rax, [rsi+38h]
0x18009ebee  test    rax, rax
0x18009ebf1  jz      loc_18009ED2B
0x18009ebf7  cmp     [rax], r15d
0x18009ebfa  jz      loc_18009ED2B
0x18009ec00  mov     eax, [rax]
0x18009ec02  mov     ecx, 0FFFFFFFFh
0x18009ec07  shl     rax, 2
0x18009ec0b  cmp     rax, rcx
0x18009ec0e  ja      loc_18009ED51
0x18009ec14  mov     rcx, cs:gDhcpHeap; hHeap
0x18009ec1b  mov     ebx, 8
0x18009ec20  mov     edx, ebx; dwFlags
0x18009ec22  mov     r8d, eax; dwBytes
0x18009ec25  mov     ebp, eax
0x18009ec27  call    cs:__imp_HeapAlloc
0x18009ec2e  nop     dword ptr [rax+rax+00h]
0x18009ec33  mov     r14, rax
0x18009ec36  test    rax, rax
0x18009ec39  jnz     short loc_18009EC79
0x18009ec3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ec42  lea     rax, WPP_GLOBAL_Control
0x18009ec49  cmp     rcx, rax
0x18009ec4c  jz      short loc_18009EC6A
0x18009ec4e  test    dword ptr [rcx+1Ch], 800000h
0x18009ec55  jz      short loc_18009EC6A
0x18009ec57  mov     rcx, [rcx+10h]
0x18009ec5b  lea     edx, [rbx+3]
0x18009ec5e  lea     r8, WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids
0x18009ec65  call    WPP_SF_
0x18009ec6a  mov     rcx, rdi
0x18009ec6d  call    DhcpDALJetRollback
0x18009ec72  mov     eax, ebx
0x18009ec74  jmp     loc_18009ED65
0x18009ec79  mov     rax, [rsi+38h]
0x18009ec7d  mov     r8d, r15d
0x18009ec80  cmp     [rax], r15d
0x18009ec83  jbe     short loc_18009EC9F
0x18009ec85  mov     rax, [rax+8]
0x18009ec89  mov     edx, r8d
0x18009ec8c  inc     r8d
0x18009ec8f  mov     ecx, [rax+rdx*4]
0x18009ec92  mov     [r14+rdx*4], ecx
0x18009ec96  mov     rax, [rsi+38h]
0x18009ec9a  cmp     r8d, [rax]
0x18009ec9d  jb      short loc_18009EC85
0x18009ec9f  mov     r8d, cs:dword_1800F7388
0x18009eca6  mov     r9, r14
0x18009eca9  mov     rdx, cs:FailoverConfTableHandle
0x18009ecb0  mov     rcx, rdi
0x18009ecb3  mov     [rsp+58h+var_38], ebp
0x18009ecb7  call    DhcpDALJetSetValue
0x18009ecbc  mov     ebx, eax
0x18009ecbe  test    eax, eax
0x18009ecc0  jnz     short loc_18009ED0B
0x18009ecc2  xor     ecx, ecx; Time
0x18009ecc4  call    cs:__imp_time
0x18009eccb  nop     dword ptr [rax+rax+00h]
0x18009ecd0  mov     r8d, cs:dword_1800F73A0
0x18009ecd7  lea     r9, [rsp+58h+arg_10]
0x18009ecdc  mov     rdx, cs:FailoverConfTableHandle
0x18009ece3  mov     rcx, rdi
0x18009ece6  mov     [rsp+58h+arg_10], eax
0x18009ecea  mov     [rsp+58h+var_38], r12d
0x18009ecef  call    DhcpDALJetSetValue
0x18009ecf4  mov     ebx, eax
0x18009ecf6  test    eax, eax
0x18009ecf8  jnz     short loc_18009ED0B
0x18009ecfa  mov     rdx, cs:FailoverConfTableHandle
0x18009ed01  mov     rcx, rdi
0x18009ed04  call    DhcpDALJetCommitUpdate
0x18009ed09  mov     ebx, eax
0x18009ed0b  mov     rcx, cs:gDhcpHeap; hHeap
0x18009ed12  mov     r8, r14; lpMem
0x18009ed15  xor     edx, edx; dwFlags
0x18009ed17  call    cs:__imp_HeapFree
0x18009ed1e  nop     dword ptr [rax+rax+00h]
0x18009ed23  test    ebx, ebx
0x18009ed25  jnz     loc_18009EC6A
0x18009ed2b  xor     edx, edx; grbit
0x18009ed2d  mov     rcx, rdi; sesid
0x18009ed30  call    cs:__imp_JetCommitTransaction
0x18009ed37  nop     dword ptr [rax+rax+00h]
0x18009ed3c  mov     ecx, eax
0x18009ed3e  lea     rdx, aDhcpdaljetcomm; "DhcpDALJetCommitTransaction"
0x18009ed45  call    DhcpDALMapJetError
0x18009ed4a  mov     ebx, eax
0x18009ed4c  jmp     loc_18009EC72
0x18009ed51  mov     ebx, 216h
0x18009ed56  jmp     loc_18009EC6A
0x18009ed5b  neg     rcx
0x18009ed5e  sbb     eax, eax
0x18009ed60  not     eax
0x18009ed62  and     eax, 57h
0x18009ed65  mov     rbx, [rsp+58h+arg_0]
0x18009ed6a  mov     rbp, [rsp+58h+arg_8]
0x18009ed6f  add     rsp, 30h
0x18009ed73  pop     r15
0x18009ed75  pop     r14
0x18009ed77  pop     r12
0x18009ed79  pop     rdi
0x18009ed7a  pop     rsi
0x18009ed7b  retn
```
