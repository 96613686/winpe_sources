# WBDBCloseDatabase(x,x,x)

- ea: `0x100279f0`
- end: `0x10027bb2`
- name: `_WBDBCloseDatabase@12`
- size: `450`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x10006a60`
- `0x10029068`
- `0x10029730`
- `0x1002df60`

## callees

- `0x1001b2f0`
- `0x1001b900`
- `0x10025ab7`
- `0x100278d3`
- `0x100279f0`
- `0x10029730`
- `0x1002a7de`
- `0x1002a907`
- `0x1002aa6e`
- `0x1002aaa4`
- `0x10032ea8`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10027a59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10027a59`

## pseudocode

```c
int __stdcall WBDBCloseDatabase(int a1, int a2, int a3)
{
  int v3; // eax
  int v4; // ebx
  int v6; // edi
  _DWORD *v7; // eax
  _DWORD *v8; // ecx
  _DWORD *v9; // eax
  _DWORD *v10; // esi
  DWORD CurrentProcessId; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // esi
  int v15; // ecx
  int v16; // esi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  _DWORD *v22; // ecx
  _DWORD *v23; // esi
  _DWORD *v24; // ecx
  _DWORD *v25; // esi
  int v26; // [esp+Ch] [ebp-Ch]
  _DWORD *v27; // [esp+10h] [ebp-8h]
  int v28; // [esp+10h] [ebp-8h]
  int v29; // [esp+14h] [ebp-4h]

  v3 = ISAMDBFindDatabaseUser(a1, a2);
  v4 = v3;
  if ( !v3 )
    return -1010;
  v6 = *(_DWORD *)(v3 + 4);
  v7 = *(_DWORD **)(v6 + 48);
  if ( v7 )
  {
    do
    {
      v8 = (_DWORD *)*v7;
      v9 = (_DWORD *)v7[5];
      v27 = v8;
      if ( v9 )
      {
        do
        {
          v10 = (_DWORD *)*v9;
          if ( v9[2] == v4 )
            WBTCloseTable(a1, v9[3]);
          v9 = v10;
        }
        while ( v10 );
        v8 = v27;
      }
      v7 = v8;
    }
    while ( v8 );
  }
  v26 = *(_DWORD *)(v4 + 8);
  CurrentProcessId = GetCurrentProcessId();
  v12 = ISAMDBFindTask(CurrentProcessId);
  (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)(v12 + 28) + 72))(
    *(_DWORD *)(*(_DWORD *)(v12 + 28) + 72),
    *(_DWORD *)(v4 + 16));
  ISAMDBDeleteDatabaseUser(v6, v4);
  v13 = 0;
  v14 = 0;
  if ( !*(_DWORD *)(v6 + 44) )
  {
    v15 = *(_DWORD *)(v6 + 12);
    if ( v15 )
    {
      if ( *(_DWORD *)(v15 + 4) == 3 || *(_DWORD *)(v15 + 4) == 4 )
      {
        v28 = 0;
        WorkbookCurrentDimensions(v15, *(_DWORD *)(v6 + 28) + 4);
      }
      else
      {
        v28 = 1;
      }
      v16 = *(_DWORD *)(v26 + 20);
      v17 = WorkbookClose(*(_DWORD *)(v6 + 12), v16 != 0);
      v13 = v17;
      if ( v16 && (v17 == -1808 || v17 == -1022) )
      {
        v18 = v6 + 72;
        while ( 1 )
        {
          v19 = (*(int (__thiscall **)(_DWORD, _DWORD, int, int))(v26 + 20))(
                  *(_DWORD *)(v26 + 20),
                  *(_DWORD *)(v26 + 16),
                  v18,
                  v13);
          v20 = *(_DWORD *)(v6 + 12);
          if ( !v19 )
            break;
          v13 = WorkbookClose(v20, v16 != 0);
          v18 = v6 + 72;
          if ( !v13 )
            goto LABEL_24;
        }
        v13 = WorkbookClose(v20, 0);
      }
LABEL_24:
      if ( v28 == 1 && !*(_DWORD *)(v6 + 28) )
      {
        v21 = *(_DWORD *)(v6 + 60);
        if ( v21 )
          *(_DWORD *)(v21 + 4) = 2;
        JetDeleteFileW((LPCWSTR)(v6 + 72));
      }
    }
    v22 = *(_DWORD **)(v6 + 28);
    if ( v22 )
    {
      do
      {
        v23 = (_DWORD *)*v22;
        MemFree(v22);
        v22 = v23;
      }
      while ( v23 );
    }
    v14 = FinishWithNetFiles(v6);
    v29 = v14;
    ISAMDBDeleteDatabase(*(_DWORD *)(v6 + 4), v6);
    v24 = dword_1003AE78;
    if ( dword_1003AE78 )
    {
      do
      {
        v25 = (_DWORD *)*v24;
        MemFree(v24);
        v24 = v25;
      }
      while ( v25 );
      v14 = v29;
    }
    dword_1003AE78 = 0;
  }
  if ( v13 )
    return v13;
  return v14;
}

```

## disassembly

```asm
0x100279f0  mov     edi, edi
0x100279f2  push    ebp
0x100279f3  mov     ebp, esp
0x100279f5  and     esp, 0FFFFFFF8h
0x100279f8  mov     ecx, [ebp+arg_0]
0x100279fb  sub     esp, 0Ch
0x100279fe  mov     edx, [ebp+arg_4]
0x10027a01  push    ebx
0x10027a02  push    esi
0x10027a03  push    edi
0x10027a04  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x10027a09  mov     ebx, eax
0x10027a0b  test    ebx, ebx
0x10027a0d  jnz     short loc_10027A19
0x10027a0f  mov     eax, 0FFFFFC0Eh
0x10027a14  jmp     loc_10027BA9
0x10027a19  mov     edi, [ebx+4]
0x10027a1c  mov     eax, [edi+30h]
0x10027a1f  test    eax, eax
0x10027a21  jz      short loc_10027A52
0x10027a23  mov     ecx, [eax]
0x10027a25  mov     eax, [eax+14h]
0x10027a28  mov     [esp+18h+var_8], ecx
0x10027a2c  test    eax, eax
0x10027a2e  jz      short loc_10027A4C
0x10027a30  mov     esi, [eax]
0x10027a32  cmp     [eax+8], ebx
0x10027a35  jnz     short loc_10027A42
0x10027a37  push    dword ptr [eax+0Ch]
0x10027a3a  push    [ebp+arg_0]
0x10027a3d  call    _WBTCloseTable@8; WBTCloseTable(x,x)
0x10027a42  mov     eax, esi
0x10027a44  test    esi, esi
0x10027a46  jnz     short loc_10027A30
0x10027a48  mov     ecx, [esp+18h+var_8]
0x10027a4c  mov     eax, ecx
0x10027a4e  test    ecx, ecx
0x10027a50  jnz     short loc_10027A23
0x10027a52  mov     eax, [ebx+8]
0x10027a55  mov     [esp+18h+var_C], eax
0x10027a59  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10027a5f  mov     ecx, eax
0x10027a61  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x10027a66  push    dword ptr [ebx+10h]
0x10027a69  mov     eax, [eax+1Ch]
0x10027a6c  mov     esi, [eax+48h]
0x10027a6f  mov     ecx, esi
0x10027a71  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10027a77  call    esi
0x10027a79  mov     edx, ebx
0x10027a7b  mov     ecx, edi
0x10027a7d  call    _ISAMDBDeleteDatabaseUser@8; ISAMDBDeleteDatabaseUser(x,x)
0x10027a82  xor     ebx, ebx
0x10027a84  xor     esi, esi
0x10027a86  cmp     [edi+2Ch], ebx
0x10027a89  jnz     loc_10027BA2
0x10027a8f  mov     ecx, [edi+0Ch]
0x10027a92  test    ecx, ecx
0x10027a94  jz      loc_10027B52
0x10027a9a  cmp     dword ptr [ecx+4], 3
0x10027a9e  jz      short loc_10027AB0
0x10027aa0  cmp     dword ptr [ecx+4], 4
0x10027aa4  jz      short loc_10027AB0
0x10027aa6  mov     [esp+18h+var_8], 1
0x10027aae  jmp     short loc_10027ABF
0x10027ab0  mov     edx, [edi+1Ch]
0x10027ab3  add     edx, 4
0x10027ab6  mov     [esp+18h+var_8], ebx
0x10027aba  call    _WorkbookCurrentDimensions@8; WorkbookCurrentDimensions(x,x)
0x10027abf  mov     esi, [esp+18h+var_C]
0x10027ac3  xor     eax, eax
0x10027ac5  mov     ecx, [edi+0Ch]
0x10027ac8  mov     esi, [esi+14h]
0x10027acb  test    esi, esi
0x10027acd  setnz   al
0x10027ad0  mov     edx, eax
0x10027ad2  mov     [esp+18h+var_4], eax
0x10027ad6  call    _WorkbookClose@8; WorkbookClose(x,x)
0x10027adb  mov     ebx, eax
0x10027add  test    esi, esi
0x10027adf  jz      short loc_10027B2E
0x10027ae1  cmp     ebx, 0FFFFF8F0h
0x10027ae7  jz      short loc_10027AF1
0x10027ae9  cmp     ebx, 0FFFFFC02h
0x10027aef  jnz     short loc_10027B2E
0x10027af1  lea     eax, [edi+48h]
0x10027af4  push    ebx
0x10027af5  push    eax
0x10027af6  mov     eax, [esp+20h+var_C]
0x10027afa  mov     esi, [eax+14h]
0x10027afd  mov     ecx, esi
0x10027aff  push    dword ptr [eax+10h]
0x10027b02  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10027b08  call    esi
0x10027b0a  mov     ecx, [edi+0Ch]
0x10027b0d  test    eax, eax
0x10027b0f  jz      short loc_10027B25
0x10027b11  mov     edx, [esp+18h+var_4]
0x10027b15  call    _WorkbookClose@8; WorkbookClose(x,x)
0x10027b1a  mov     ebx, eax
0x10027b1c  lea     eax, [edi+48h]
0x10027b1f  test    ebx, ebx
0x10027b21  jnz     short loc_10027AF4
0x10027b23  jmp     short loc_10027B2E
0x10027b25  xor     edx, edx
0x10027b27  call    _WorkbookClose@8; WorkbookClose(x,x)
0x10027b2c  mov     ebx, eax
0x10027b2e  cmp     [esp+18h+var_8], 1
0x10027b33  jnz     short loc_10027B52
0x10027b35  cmp     dword ptr [edi+1Ch], 0
0x10027b39  jnz     short loc_10027B52
0x10027b3b  mov     eax, [edi+3Ch]
0x10027b3e  test    eax, eax
0x10027b40  jz      short loc_10027B49
0x10027b42  mov     dword ptr [eax+4], 2
0x10027b49  lea     eax, [edi+48h]
0x10027b4c  push    eax; lpFileName
0x10027b4d  call    _JetDeleteFileW@4; JetDeleteFileW(x)
0x10027b52  mov     ecx, [edi+1Ch]
0x10027b55  test    ecx, ecx
0x10027b57  jz      short loc_10027B66
0x10027b59  mov     esi, [ecx]
0x10027b5b  call    _MemFree@4; MemFree(x)
0x10027b60  mov     ecx, esi
0x10027b62  test    esi, esi
0x10027b64  jnz     short loc_10027B59
0x10027b66  mov     ecx, edi
0x10027b68  call    FinishWithNetFiles
0x10027b6d  mov     ecx, [edi+4]
0x10027b70  mov     esi, eax
0x10027b72  mov     edx, edi
0x10027b74  mov     [esp+18h+var_4], esi
0x10027b78  call    _ISAMDBDeleteDatabase@8; ISAMDBDeleteDatabase(x,x)
0x10027b7d  mov     ecx, dword_1003AE78
0x10027b83  test    ecx, ecx
0x10027b85  jz      short loc_10027B98
0x10027b87  mov     esi, [ecx]
0x10027b89  call    _MemFree@4; MemFree(x)
0x10027b8e  mov     ecx, esi
0x10027b90  test    esi, esi
0x10027b92  jnz     short loc_10027B87
0x10027b94  mov     esi, [esp+18h+var_4]
0x10027b98  mov     dword_1003AE78, 0
0x10027ba2  test    ebx, ebx
0x10027ba4  cmovnz  esi, ebx
0x10027ba7  mov     eax, esi
0x10027ba9  pop     edi
0x10027baa  pop     esi
0x10027bab  pop     ebx
0x10027bac  mov     esp, ebp
0x10027bae  pop     ebp
0x10027baf  retn    0Ch
```
