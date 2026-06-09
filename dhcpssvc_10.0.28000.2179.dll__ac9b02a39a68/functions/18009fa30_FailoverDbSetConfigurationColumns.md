# FailoverDbSetConfigurationColumns

- ea: `0x18009fa30`
- end: `0x18009fd10`
- name: `FailoverDbSetConfigurationColumns`
- size: `736`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009ed58`

## callees

- `0x180003228`
- `0x18009fa30`
- `0x1800a03f0`
- `0x1800a0448`
- `0x1800a0b3c`
- `0x1800a0b68`
- `0x1800a0bac`

## import_xrefs

- `msvcrt!time` at `0x18009fb8c`
- `msvcrt!time` at `0x18009fb8c`
- `ESENT!JetCommitTransaction` at `0x18009fcc9`
- `ESENT!JetCommitTransaction` at `0x18009fcc9`
- `KERNEL32!HeapAlloc` at `0x18009fbfd`
- `KERNEL32!HeapAlloc` at `0x18009fbfd`
- `KERNEL32!HeapFree` at `0x18009fcb4`
- `KERNEL32!HeapFree` at `0x18009fcb4`

## string_xrefs

- `0x18009fcd7`: `DhcpDALJetCommitTransaction`

## pseudocode

```c
__int64 __fastcall FailoverDbSetConfigurationColumns(JET_SESID sesid, __int64 a2, __int16 a3)
{
  _DWORD *v6; // r14
  unsigned int v7; // ebx
  unsigned __int64 v8; // rsi
  __int64 v9; // rax
  __int64 i; // r8
  unsigned int v11; // eax
  int v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v6 = 0;
  v7 = DhcpDALJetBeginTransaction(sesid);
  if ( v7 )
    goto LABEL_30;
  if ( (a3 & 1) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9448, (int)a2 + 24, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 2) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9460, (int)a2 + 28, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 0x10) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F93E8, (int)a2 + 8, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 8) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9400, (int)a2 + 64, 1u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 4) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9418, (int)a2 + 16, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  if ( (a3 & 0x20) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9430, (int)a2 + 20, 4u);
    if ( v7 )
      goto LABEL_30;
  }
  v13 = time(0);
  if ( (a3 & 0x800) != 0 )
  {
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9490, (unsigned int)&v13, 4u);
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
  v6 = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v8);
  if ( v6 )
  {
    v9 = *(_QWORD *)(a2 + 56);
    for ( i = 0; (unsigned int)i < *(_DWORD *)v9; v9 = *(_QWORD *)(a2 + 56) )
    {
      v6[i] = *(_DWORD *)(*(_QWORD *)(v9 + 8) + 4 * i);
      i = (unsigned int)(i + 1);
    }
    v7 = DhcpDALJetSetValue(sesid, FailoverConfTableHandle, dword_1800F9478, (_DWORD)v6, v8);
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
  v11 = JetCommitTransaction(sesid, 0);
  return (unsigned int)DhcpDALMapJetError(v11, "DhcpDALJetCommitTransaction");
}

```

## disassembly

```asm
0x18009fa30  mov     rax, rsp
0x18009fa33  mov     [rax+8], rbx
0x18009fa37  mov     [rax+10h], rbp
0x18009fa3b  mov     [rax+18h], rsi
0x18009fa3f  push    rdi
0x18009fa40  push    r14
0x18009fa42  push    r15
0x18009fa44  sub     rsp, 40h
0x18009fa48  mov     esi, r8d
0x18009fa4b  mov     dword ptr [rax+20h], 0
0x18009fa52  mov     rbp, rdx
0x18009fa55  mov     rdi, rcx
0x18009fa58  xor     r14d, r14d
0x18009fa5b  call    DhcpDALJetBeginTransaction
0x18009fa60  mov     ebx, eax
0x18009fa62  test    eax, eax
0x18009fa64  jnz     loc_18009FCEC
0x18009fa6a  lea     r15d, [r14+4]
0x18009fa6e  test    sil, 1
0x18009fa72  jz      short loc_18009FA9D
0x18009fa74  mov     r8d, cs:dword_1800F9448
0x18009fa7b  lea     r9, [rbp+18h]
0x18009fa7f  mov     rdx, cs:FailoverConfTableHandle
0x18009fa86  mov     rcx, rdi
0x18009fa89  mov     [rsp+58h+var_38], r15d
0x18009fa8e  call    DhcpDALJetSetValue
0x18009fa93  mov     ebx, eax
0x18009fa95  test    eax, eax
0x18009fa97  jnz     loc_18009FCEC
0x18009fa9d  test    sil, 2
0x18009faa1  jz      short loc_18009FACC
0x18009faa3  mov     r8d, cs:dword_1800F9460
0x18009faaa  lea     r9, [rbp+1Ch]
0x18009faae  mov     rdx, cs:FailoverConfTableHandle
0x18009fab5  mov     rcx, rdi
0x18009fab8  mov     [rsp+58h+var_38], r15d
0x18009fabd  call    DhcpDALJetSetValue
0x18009fac2  mov     ebx, eax
0x18009fac4  test    eax, eax
0x18009fac6  jnz     loc_18009FCEC
0x18009facc  test    sil, 10h
0x18009fad0  jz      short loc_18009FAFB
0x18009fad2  mov     r8d, cs:dword_1800F93E8
0x18009fad9  lea     r9, [rbp+8]
0x18009fadd  mov     rdx, cs:FailoverConfTableHandle
0x18009fae4  mov     rcx, rdi
0x18009fae7  mov     [rsp+58h+var_38], r15d
0x18009faec  call    DhcpDALJetSetValue
0x18009faf1  mov     ebx, eax
0x18009faf3  test    eax, eax
0x18009faf5  jnz     loc_18009FCEC
0x18009fafb  test    sil, 8
0x18009faff  jz      short loc_18009FB2D
0x18009fb01  mov     r8d, cs:dword_1800F9400
0x18009fb08  lea     r9, [rbp+40h]
0x18009fb0c  mov     rdx, cs:FailoverConfTableHandle
0x18009fb13  mov     rcx, rdi
0x18009fb16  mov     [rsp+58h+var_38], 1
0x18009fb1e  call    DhcpDALJetSetValue
0x18009fb23  mov     ebx, eax
0x18009fb25  test    eax, eax
0x18009fb27  jnz     loc_18009FCEC
0x18009fb2d  test    r15b, sil
0x18009fb30  jz      short loc_18009FB5B
0x18009fb32  mov     r8d, cs:dword_1800F9418
0x18009fb39  lea     r9, [rbp+10h]
0x18009fb3d  mov     rdx, cs:FailoverConfTableHandle
0x18009fb44  mov     rcx, rdi
0x18009fb47  mov     [rsp+58h+var_38], r15d
0x18009fb4c  call    DhcpDALJetSetValue
0x18009fb51  mov     ebx, eax
0x18009fb53  test    eax, eax
0x18009fb55  jnz     loc_18009FCEC
0x18009fb5b  test    sil, 20h
0x18009fb5f  jz      short loc_18009FB8A
0x18009fb61  mov     r8d, cs:dword_1800F9430
0x18009fb68  lea     r9, [rbp+14h]
0x18009fb6c  mov     rdx, cs:FailoverConfTableHandle
0x18009fb73  mov     rcx, rdi
0x18009fb76  mov     [rsp+58h+var_38], r15d
0x18009fb7b  call    DhcpDALJetSetValue
0x18009fb80  mov     ebx, eax
0x18009fb82  test    eax, eax
0x18009fb84  jnz     loc_18009FCEC
0x18009fb8a  xor     ecx, ecx; Time
0x18009fb8c  call    cs:__imp_time
0x18009fb93  nop     dword ptr [rax+rax+00h]
0x18009fb98  mov     [rsp+58h+arg_18], eax
0x18009fb9c  bt      esi, 0Bh
0x18009fba0  jnb     short loc_18009FBCC
0x18009fba2  mov     r8d, cs:dword_1800F9490
0x18009fba9  lea     r9, [rsp+58h+arg_18]
0x18009fbae  mov     rdx, cs:FailoverConfTableHandle
0x18009fbb5  mov     rcx, rdi
0x18009fbb8  mov     [rsp+58h+var_38], r15d
0x18009fbbd  call    DhcpDALJetSetValue
0x18009fbc2  mov     ebx, eax
0x18009fbc4  test    eax, eax
0x18009fbc6  jnz     loc_18009FCEC
0x18009fbcc  bt      esi, 0Ah
0x18009fbd0  jnb     loc_18009FC92
0x18009fbd6  mov     rax, [rbp+38h]
0x18009fbda  mov     esi, [rax]
0x18009fbdc  mov     eax, 0FFFFFFFFh
0x18009fbe1  shl     rsi, 2
0x18009fbe5  cmp     rsi, rax
0x18009fbe8  ja      loc_18009FCE7
0x18009fbee  mov     rcx, cs:gDhcpHeap; hHeap
0x18009fbf5  mov     edx, 8; dwFlags
0x18009fbfa  mov     r8d, esi; dwBytes
0x18009fbfd  call    cs:__imp_HeapAlloc
0x18009fc04  nop     dword ptr [rax+rax+00h]
0x18009fc09  mov     r14, rax
0x18009fc0c  test    rax, rax
0x18009fc0f  jnz     short loc_18009FC4B
0x18009fc11  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fc18  lea     rax, WPP_GLOBAL_Control
0x18009fc1f  cmp     rcx, rax
0x18009fc22  jz      loc_18009FCC0
0x18009fc28  test    dword ptr [rcx+1Ch], 800000h
0x18009fc2f  jz      loc_18009FCC0
0x18009fc35  mov     rcx, [rcx+10h]
0x18009fc39  lea     edx, [r14+0Ah]
0x18009fc3d  lea     r8, WPP_69eab83df91b31eacaf8ec0f641a7f07_Traceguids
0x18009fc44  call    WPP_SF_
0x18009fc49  jmp     short loc_18009FCC0
0x18009fc4b  mov     rax, [rbp+38h]
0x18009fc4f  xor     r8d, r8d
0x18009fc52  cmp     [rax], r8d
0x18009fc55  jbe     short loc_18009FC6F
0x18009fc57  mov     rax, [rax+8]
0x18009fc5b  mov     ecx, [rax+r8*4]
0x18009fc5f  mov     [r14+r8*4], ecx
0x18009fc63  inc     r8d
0x18009fc66  mov     rax, [rbp+38h]
0x18009fc6a  cmp     r8d, [rax]
0x18009fc6d  jb      short loc_18009FC57
0x18009fc6f  mov     r8d, cs:dword_1800F9478
0x18009fc76  mov     r9, r14
0x18009fc79  mov     rdx, cs:FailoverConfTableHandle
0x18009fc80  mov     rcx, rdi
0x18009fc83  mov     [rsp+58h+var_38], esi
0x18009fc87  call    DhcpDALJetSetValue
0x18009fc8c  mov     ebx, eax
0x18009fc8e  test    eax, eax
0x18009fc90  jnz     short loc_18009FCA8
0x18009fc92  mov     rdx, cs:FailoverConfTableHandle
0x18009fc99  mov     rcx, rdi
0x18009fc9c  call    DhcpDALJetCommitUpdate
0x18009fca1  mov     ebx, eax
0x18009fca3  test    r14, r14
0x18009fca6  jz      short loc_18009FCC0
0x18009fca8  mov     rcx, cs:gDhcpHeap; hHeap
0x18009fcaf  mov     r8, r14; lpMem
0x18009fcb2  xor     edx, edx; dwFlags
0x18009fcb4  call    cs:__imp_HeapFree
0x18009fcbb  nop     dword ptr [rax+rax+00h]
0x18009fcc0  test    ebx, ebx
0x18009fcc2  jnz     short loc_18009FCEC
0x18009fcc4  xor     edx, edx; grbit
0x18009fcc6  mov     rcx, rdi; sesid
0x18009fcc9  call    cs:__imp_JetCommitTransaction
0x18009fcd0  nop     dword ptr [rax+rax+00h]
0x18009fcd5  mov     ecx, eax
0x18009fcd7  lea     rdx, aDhcpdaljetcomm; "DhcpDALJetCommitTransaction"
0x18009fcde  call    DhcpDALMapJetError
0x18009fce3  mov     ebx, eax
0x18009fce5  jmp     short loc_18009FCF4
0x18009fce7  mov     ebx, 216h
0x18009fcec  mov     rcx, rdi
0x18009fcef  call    DhcpDALJetRollback
0x18009fcf4  mov     rbp, [rsp+58h+arg_8]
0x18009fcf9  mov     eax, ebx
0x18009fcfb  mov     rbx, [rsp+58h+arg_0]
0x18009fd00  mov     rsi, [rsp+58h+arg_10]
0x18009fd05  add     rsp, 40h
0x18009fd09  pop     r15
0x18009fd0b  pop     r14
0x18009fd0d  pop     rdi
0x18009fd0e  retn
```
