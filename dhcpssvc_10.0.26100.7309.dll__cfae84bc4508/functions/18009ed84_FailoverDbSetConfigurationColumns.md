# FailoverDbSetConfigurationColumns

- ea: `0x18009ed84`
- end: `0x18009f063`
- name: `FailoverDbSetConfigurationColumns`
- size: `735`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009e0b8`

## callees

- `0x18000323c`
- `0x18009ed84`
- `0x18009f738`
- `0x18009f790`
- `0x18009fe78`
- `0x18009fea4`
- `0x18009fee0`

## import_xrefs

- `msvcrt!time` at `0x18009eedd`
- `msvcrt!time` at `0x18009eedd`
- `ESENT!JetCommitTransaction` at `0x18009f01c`
- `ESENT!JetCommitTransaction` at `0x18009f01c`
- `KERNEL32!HeapAlloc` at `0x18009ef50`
- `KERNEL32!HeapAlloc` at `0x18009ef50`
- `KERNEL32!HeapFree` at `0x18009f007`
- `KERNEL32!HeapFree` at `0x18009f007`

## string_xrefs

- `0x18009f02a`: `DhcpDALJetCommitTransaction`

## pseudocode

```c
__int64 __fastcall FailoverDbSetConfigurationColumns(JET_SESID sesid, __int64 a2, __int16 a3)
{
  _DWORD *v6; // r14
  unsigned int v7; // ebx
  unsigned __int64 v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // rax
  __int64 i; // r8
  unsigned int v12; // eax
  int v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  v6 = 0;
  v7 = DhcpDALJetBeginTransaction(sesid);
  if ( v7 )
    goto LABEL_30;
  if ( (a3 & 1) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7358, (int)a2 + 24, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 2) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7370, (int)a2 + 28, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 0x10) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F72F8, (int)a2 + 8, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 8) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7310, (int)a2 + 64, 1u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 4) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7328, (int)a2 + 16, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 0x20) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7340, (int)a2 + 20, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  v14 = time(0);
  if ( (a3 & 0x800) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F73A0, (unsigned int)&v14, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 0x400) == 0 )
    goto LABEL_25;
  v8 = 4LL * **(unsigned int **)(a2 + 56);
  if ( v8 > 0xFFFFFFFF )
  {
    v7 = 534;
    goto LABEL_30;
  }
  v9 = 4 * **(_DWORD **)(a2 + 56);
  v6 = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v8);
  if ( v6 )
  {
    v10 = *(_QWORD *)(a2 + 56);
    for ( i = 0; (unsigned int)i < *(_DWORD *)v10; v10 = *(_QWORD *)(a2 + 56) )
    {
      v6[i] = *(_DWORD *)(*(_QWORD *)(v10 + 8) + 4 * i);
      i = (unsigned int)(i + 1);
    }
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F7388, (_DWORD)v6, v9);
    if ( v7 )
    {
LABEL_26:
      HeapFree(gDhcpHeap, 0, v6);
      goto LABEL_27;
    }
LABEL_25:
    v7 = DhcpDALJetCommitUpdate(sesid, FailoverConfTableHandle);
    if ( !v6 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids);
LABEL_27:
  if ( v7 )
  {
LABEL_30:
    DhcpDALJetRollback(sesid);
    return v7;
  }
  v12 = JetCommitTransaction(sesid, 0);
  return (unsigned int)DhcpDALMapJetError(v12, "DhcpDALJetCommitTransaction");
}

```

## disassembly

```asm
0x18009ed84  mov     rax, rsp
0x18009ed87  mov     [rax+8], rbx
0x18009ed8b  mov     [rax+10h], rbp
0x18009ed8f  mov     [rax+18h], rsi
0x18009ed93  push    rdi
0x18009ed94  push    r14
0x18009ed96  push    r15
0x18009ed98  sub     rsp, 40h
0x18009ed9c  and     dword ptr [rax+20h], 0
0x18009eda0  mov     esi, r8d
0x18009eda3  mov     rbp, rdx
0x18009eda6  mov     rdi, rcx
0x18009eda9  xor     r14d, r14d
0x18009edac  call    DhcpDALJetBeginTransaction
0x18009edb1  mov     ebx, eax
0x18009edb3  test    eax, eax
0x18009edb5  jnz     loc_18009F03F
0x18009edbb  lea     r15d, [r14+4]
0x18009edbf  test    sil, 1
0x18009edc3  jz      short loc_18009EDEE
0x18009edc5  mov     r8d, cs:dword_1800F7358
0x18009edcc  lea     r9, [rbp+18h]
0x18009edd0  mov     rdx, cs:FailoverConfTableHandle
0x18009edd7  mov     rcx, rdi
0x18009edda  mov     [rsp+58h+var_38], r15d
0x18009eddf  call    DhcpDALJetSetValue
0x18009ede4  mov     ebx, eax
0x18009ede6  test    eax, eax
0x18009ede8  jnz     loc_18009F03F
0x18009edee  test    sil, 2
0x18009edf2  jz      short loc_18009EE1D
0x18009edf4  mov     r8d, cs:dword_1800F7370
0x18009edfb  lea     r9, [rbp+1Ch]
0x18009edff  mov     rdx, cs:FailoverConfTableHandle
0x18009ee06  mov     rcx, rdi
0x18009ee09  mov     [rsp+58h+var_38], r15d
0x18009ee0e  call    DhcpDALJetSetValue
0x18009ee13  mov     ebx, eax
0x18009ee15  test    eax, eax
0x18009ee17  jnz     loc_18009F03F
0x18009ee1d  test    sil, 10h
0x18009ee21  jz      short loc_18009EE4C
0x18009ee23  mov     r8d, cs:dword_1800F72F8
0x18009ee2a  lea     r9, [rbp+8]
0x18009ee2e  mov     rdx, cs:FailoverConfTableHandle
0x18009ee35  mov     rcx, rdi
0x18009ee38  mov     [rsp+58h+var_38], r15d
0x18009ee3d  call    DhcpDALJetSetValue
0x18009ee42  mov     ebx, eax
0x18009ee44  test    eax, eax
0x18009ee46  jnz     loc_18009F03F
0x18009ee4c  test    sil, 8
0x18009ee50  jz      short loc_18009EE7E
0x18009ee52  mov     r8d, cs:dword_1800F7310
0x18009ee59  lea     r9, [rbp+40h]
0x18009ee5d  mov     rdx, cs:FailoverConfTableHandle
0x18009ee64  mov     rcx, rdi
0x18009ee67  mov     [rsp+58h+var_38], 1
0x18009ee6f  call    DhcpDALJetSetValue
0x18009ee74  mov     ebx, eax
0x18009ee76  test    eax, eax
0x18009ee78  jnz     loc_18009F03F
0x18009ee7e  test    r15b, sil
0x18009ee81  jz      short loc_18009EEAC
0x18009ee83  mov     r8d, cs:dword_1800F7328
0x18009ee8a  lea     r9, [rbp+10h]
0x18009ee8e  mov     rdx, cs:FailoverConfTableHandle
0x18009ee95  mov     rcx, rdi
0x18009ee98  mov     [rsp+58h+var_38], r15d
0x18009ee9d  call    DhcpDALJetSetValue
0x18009eea2  mov     ebx, eax
0x18009eea4  test    eax, eax
0x18009eea6  jnz     loc_18009F03F
0x18009eeac  test    sil, 20h
0x18009eeb0  jz      short loc_18009EEDB
0x18009eeb2  mov     r8d, cs:dword_1800F7340
0x18009eeb9  lea     r9, [rbp+14h]
0x18009eebd  mov     rdx, cs:FailoverConfTableHandle
0x18009eec4  mov     rcx, rdi
0x18009eec7  mov     [rsp+58h+var_38], r15d
0x18009eecc  call    DhcpDALJetSetValue
0x18009eed1  mov     ebx, eax
0x18009eed3  test    eax, eax
0x18009eed5  jnz     loc_18009F03F
0x18009eedb  xor     ecx, ecx; Time
0x18009eedd  call    cs:__imp_time
0x18009eee4  nop     dword ptr [rax+rax+00h]
0x18009eee9  mov     [rsp+58h+arg_18], eax
0x18009eeed  bt      esi, 0Bh
0x18009eef1  jnb     short loc_18009EF1D
0x18009eef3  mov     r8d, cs:dword_1800F73A0
0x18009eefa  lea     r9, [rsp+58h+arg_18]
0x18009eeff  mov     rdx, cs:FailoverConfTableHandle
0x18009ef06  mov     rcx, rdi
0x18009ef09  mov     [rsp+58h+var_38], r15d
0x18009ef0e  call    DhcpDALJetSetValue
0x18009ef13  mov     ebx, eax
0x18009ef15  test    eax, eax
0x18009ef17  jnz     loc_18009F03F
0x18009ef1d  bt      esi, 0Ah
0x18009ef21  jnb     loc_18009EFE5
0x18009ef27  mov     rax, [rbp+38h]
0x18009ef2b  mov     ecx, [rax]
0x18009ef2d  mov     eax, 0FFFFFFFFh
0x18009ef32  shl     rcx, 2
0x18009ef36  cmp     rcx, rax
0x18009ef39  ja      loc_18009F03A
0x18009ef3f  mov     esi, ecx
0x18009ef41  mov     edx, 8; dwFlags
0x18009ef46  mov     r8d, ecx; dwBytes
0x18009ef49  mov     rcx, cs:gDhcpHeap; hHeap
0x18009ef50  call    cs:__imp_HeapAlloc
0x18009ef57  nop     dword ptr [rax+rax+00h]
0x18009ef5c  mov     r14, rax
0x18009ef5f  test    rax, rax
0x18009ef62  jnz     short loc_18009EF9E
0x18009ef64  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ef6b  lea     rax, WPP_GLOBAL_Control
0x18009ef72  cmp     rcx, rax
0x18009ef75  jz      loc_18009F013
0x18009ef7b  test    dword ptr [rcx+1Ch], 800000h
0x18009ef82  jz      loc_18009F013
0x18009ef88  mov     rcx, [rcx+10h]
0x18009ef8c  lea     edx, [r14+0Ah]
0x18009ef90  lea     r8, WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids
0x18009ef97  call    WPP_SF_
0x18009ef9c  jmp     short loc_18009F013
0x18009ef9e  mov     rax, [rbp+38h]
0x18009efa2  xor     r8d, r8d
0x18009efa5  cmp     [rax], r8d
0x18009efa8  jbe     short loc_18009EFC2
0x18009efaa  mov     rax, [rax+8]
0x18009efae  mov     ecx, [rax+r8*4]
0x18009efb2  mov     [r14+r8*4], ecx
0x18009efb6  inc     r8d
0x18009efb9  mov     rax, [rbp+38h]
0x18009efbd  cmp     r8d, [rax]
0x18009efc0  jb      short loc_18009EFAA
0x18009efc2  mov     r8d, cs:dword_1800F7388
0x18009efc9  mov     r9, r14
0x18009efcc  mov     rdx, cs:FailoverConfTableHandle
0x18009efd3  mov     rcx, rdi
0x18009efd6  mov     [rsp+58h+var_38], esi
0x18009efda  call    DhcpDALJetSetValue
0x18009efdf  mov     ebx, eax
0x18009efe1  test    eax, eax
0x18009efe3  jnz     short loc_18009EFFB
0x18009efe5  mov     rdx, cs:FailoverConfTableHandle
0x18009efec  mov     rcx, rdi
0x18009efef  call    DhcpDALJetCommitUpdate
0x18009eff4  mov     ebx, eax
0x18009eff6  test    r14, r14
0x18009eff9  jz      short loc_18009F013
0x18009effb  mov     rcx, cs:gDhcpHeap; hHeap
0x18009f002  mov     r8, r14; lpMem
0x18009f005  xor     edx, edx; dwFlags
0x18009f007  call    cs:__imp_HeapFree
0x18009f00e  nop     dword ptr [rax+rax+00h]
0x18009f013  test    ebx, ebx
0x18009f015  jnz     short loc_18009F03F
0x18009f017  xor     edx, edx; grbit
0x18009f019  mov     rcx, rdi; sesid
0x18009f01c  call    cs:__imp_JetCommitTransaction
0x18009f023  nop     dword ptr [rax+rax+00h]
0x18009f028  mov     ecx, eax
0x18009f02a  lea     rdx, aDhcpdaljetcomm; "DhcpDALJetCommitTransaction"
0x18009f031  call    DhcpDALMapJetError
0x18009f036  mov     ebx, eax
0x18009f038  jmp     short loc_18009F047
0x18009f03a  mov     ebx, 216h
0x18009f03f  mov     rcx, rdi
0x18009f042  call    DhcpDALJetRollback
0x18009f047  mov     rbp, [rsp+58h+arg_8]
0x18009f04c  mov     eax, ebx
0x18009f04e  mov     rbx, [rsp+58h+arg_0]
0x18009f053  mov     rsi, [rsp+58h+arg_10]
0x18009f058  add     rsp, 40h
0x18009f05c  pop     r15
0x18009f05e  pop     r14
0x18009f060  pop     rdi
0x18009f061  retn
```
