# NfsUpCallpPasswdGroupValidateGroupInfoForDuplicates

- ea: `0x140011b54`
- end: `0x140011ce6`
- name: `NfsUpCallpPasswdGroupValidateGroupInfoForDuplicates`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400114ac`

## callees

- `0x140011b54`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140011cd6`
- `ADVAPI32!EventWrite` at `0x140011cd6`
- `ADVAPI32!EventEnabled` at `0x140011c5c`
- `ADVAPI32!EventEnabled` at `0x140011cb4`
- `ADVAPI32!EventEnabled` at `0x140011c5c`
- `ADVAPI32!EventEnabled` at `0x140011cb4`
- `ntdll!RtlCompareUnicodeString` at `0x140011bcc`
- `ntdll!RtlCompareUnicodeString` at `0x140011bcc`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupValidateGroupInfoForDuplicates(__int64 a1, __int64 *a2, __int64 a3)
{
  unsigned int v3; // eax
  unsigned int v6; // edx
  __int64 v7; // r10
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned int v10; // edx
  __int64 v11; // rsi
  __int64 v12; // r14
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  __int64 v16; // rax
  ULONG v17; // r8d
  const EVENT_DESCRIPTOR *v18; // rdx
  __int64 v19; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-48h] BYREF
  __int64 v21; // [rsp+30h] [rbp-38h]
  int v22; // [rsp+38h] [rbp-30h]
  int v23; // [rsp+3Ch] [rbp-2Ch]
  __int64 v24; // [rsp+40h] [rbp-28h]
  int v25; // [rsp+48h] [rbp-20h]
  int v26; // [rsp+4Ch] [rbp-1Ch]

  v3 = *((_DWORD *)a2 + 6);
  if ( v3 < 2 )
    return 0;
  v6 = v3 - 1;
  v7 = a2[1];
  v8 = 0;
  while ( 1 )
  {
    v9 = (unsigned int)(v8 + 1);
    if ( *(_DWORD *)(*(_QWORD *)(v7 + 8 * v8) + 20LL) == *(_DWORD *)(*(_QWORD *)(v7 + 8 * v9) + 20LL) )
      break;
    v8 = (unsigned int)v9;
    if ( (unsigned int)v9 >= v6 )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = v10 + 1;
        v12 = v10;
        if ( !RtlCompareUnicodeString(*(PCUNICODE_STRING *)(*a2 + 8LL * v10), *(PCUNICODE_STRING *)(*a2 + 8 * v11), 1u) )
          break;
        v10 = v11;
        if ( (unsigned int)v11 >= *((_DWORD *)a2 + 6) - 1 )
          return 0;
      }
      v14 = *a2;
      UserData.Ptr = *(_QWORD *)(*a2 + 8 * v12);
      *(_QWORD *)&UserData.Size = 2;
      v15 = *(unsigned __int16 **)(v14 + 8 * v12);
      LODWORD(v14) = *v15;
      v21 = *((_QWORD *)v15 + 1);
      v16 = -1;
      v22 = v14;
      v23 = 0;
      v24 = a3;
      do
        ++v16;
      while ( *(_WORD *)(a3 + 2 * v16) );
      v25 = 2 * v16 + 2;
      v26 = 0;
      if ( RegHandle && EventEnabled(RegHandle, &EVENT_NFS_SERVICE_DUPLICATE_NAME_IN_FILE) )
      {
        v17 = 3;
        v18 = &EVENT_NFS_SERVICE_DUPLICATE_NAME_IN_FILE;
LABEL_20:
        EventWrite(RegHandle, v18, v17, &UserData);
        return 13;
      }
      return 13;
    }
  }
  UserData.Ptr = *(_QWORD *)(v7 + 8 * v8) + 20LL;
  v19 = -1;
  *(_QWORD *)&UserData.Size = 4;
  v21 = a3;
  do
    ++v19;
  while ( *(_WORD *)(a3 + 2 * v19) );
  v22 = 2 * v19 + 2;
  v23 = 0;
  if ( RegHandle && EventEnabled(RegHandle, &EVENT_NFS_SERVICE_DUPLICATE_ID_IN_FILE) )
  {
    v17 = 2;
    v18 = &EVENT_NFS_SERVICE_DUPLICATE_ID_IN_FILE;
    goto LABEL_20;
  }
  return 13;
}

```

## disassembly

```asm
0x140011b54  push    rbp
0x140011b56  push    rbx
0x140011b57  push    rsi
0x140011b58  push    rdi
0x140011b59  push    r14
0x140011b5b  push    r15
0x140011b5d  mov     rbp, rsp
0x140011b60  sub     rsp, 68h
0x140011b64  mov     rax, cs:__security_cookie
0x140011b6b  xor     rax, rsp
0x140011b6e  mov     [rbp+var_18], rax
0x140011b72  mov     eax, [rdx+18h]
0x140011b75  mov     rdi, r8
0x140011b78  mov     rbx, rdx
0x140011b7b  cmp     eax, 2
0x140011b7e  jb      short loc_140011BE1
0x140011b80  lea     edx, [rax-1]
0x140011b83  xor     r15d, r15d
0x140011b86  test    edx, edx
0x140011b88  jz      short loc_140011BE1
0x140011b8a  mov     r10, [rbx+8]
0x140011b8e  mov     eax, r15d
0x140011b91  mov     r8, [r10+rax*8]
0x140011b95  lea     r9d, [rax+1]
0x140011b99  mov     rcx, [r10+r9*8]
0x140011b9d  add     r8, 14h
0x140011ba1  mov     eax, [rcx+14h]
0x140011ba4  cmp     [r8], eax
0x140011ba7  jz      loc_140011C75
0x140011bad  mov     eax, r9d
0x140011bb0  cmp     r9d, edx
0x140011bb3  jb      short loc_140011B91
0x140011bb5  mov     edx, r15d
0x140011bb8  mov     rcx, [rbx]
0x140011bbb  lea     esi, [rdx+1]
0x140011bbe  mov     r14d, edx
0x140011bc1  mov     r8b, 1; CaseInsensitive
0x140011bc4  mov     rdx, [rcx+rsi*8]; String2
0x140011bc8  mov     rcx, [rcx+r14*8]; String1
0x140011bcc  call    cs:__imp_RtlCompareUnicodeString
0x140011bd2  test    eax, eax
0x140011bd4  jz      short loc_140011BFC
0x140011bd6  mov     eax, [rbx+18h]
0x140011bd9  mov     edx, esi
0x140011bdb  dec     eax
0x140011bdd  cmp     esi, eax
0x140011bdf  jb      short loc_140011BB8
0x140011be1  xor     eax, eax
0x140011be3  mov     rcx, [rbp+var_18]
0x140011be7  xor     rcx, rsp; StackCookie
0x140011bea  call    __security_check_cookie
0x140011bef  add     rsp, 68h
0x140011bf3  pop     r15
0x140011bf5  pop     r14
0x140011bf7  pop     rdi
0x140011bf8  pop     rsi
0x140011bf9  pop     rbx
0x140011bfa  pop     rbp
0x140011bfb  retn
0x140011bfc  mov     rcx, [rbx]
0x140011bff  mov     rax, [rcx+r14*8]
0x140011c03  mov     [rbp+UserData.Ptr], rax
0x140011c07  mov     qword ptr [rbp+UserData.Size], 2
0x140011c0f  mov     rax, [rcx+r14*8]
0x140011c13  movzx   ecx, word ptr [rax]
0x140011c16  mov     rax, [rax+8]
0x140011c1a  mov     [rbp+var_38], rax
0x140011c1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011c22  mov     [rbp+var_30], ecx
0x140011c25  mov     [rbp+var_2C], r15d
0x140011c29  mov     [rbp+var_28], rdi
0x140011c2d  inc     rax
0x140011c30  cmp     [rdi+rax*2], r15w
0x140011c35  jnz     short loc_140011C2D
0x140011c37  mov     rcx, cs:RegHandle; RegHandle
0x140011c3e  lea     eax, ds:2[rax*2]
0x140011c45  mov     [rbp+var_20], eax
0x140011c48  mov     [rbp+var_1C], r15d
0x140011c4c  test    rcx, rcx
0x140011c4f  jz      loc_140011CDC
0x140011c55  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_NAME_IN_FILE; EventDescriptor
0x140011c5c  call    cs:__imp_EventEnabled
0x140011c62  test    al, al
0x140011c64  jz      short loc_140011CDC
0x140011c66  mov     r8d, 3
0x140011c6c  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_NAME_IN_FILE
0x140011c73  jmp     short loc_140011CCB
0x140011c75  mov     [rbp+UserData.Ptr], r8
0x140011c79  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011c7d  mov     qword ptr [rbp+UserData.Size], 4
0x140011c85  mov     [rbp+var_38], rdi
0x140011c89  inc     rax
0x140011c8c  cmp     [rdi+rax*2], r15w
0x140011c91  jnz     short loc_140011C89
0x140011c93  mov     rcx, cs:RegHandle; RegHandle
0x140011c9a  lea     eax, ds:2[rax*2]
0x140011ca1  mov     [rbp+var_30], eax
0x140011ca4  mov     [rbp+var_2C], r15d
0x140011ca8  test    rcx, rcx
0x140011cab  jz      short loc_140011CDC
0x140011cad  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_ID_IN_FILE; EventDescriptor
0x140011cb4  call    cs:__imp_EventEnabled
0x140011cba  test    al, al
0x140011cbc  jz      short loc_140011CDC
0x140011cbe  mov     r8d, 2; UserDataCount
0x140011cc4  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_ID_IN_FILE; EventDescriptor
0x140011ccb  mov     rcx, cs:RegHandle; RegHandle
0x140011cd2  lea     r9, [rbp+UserData]; UserData
0x140011cd6  call    cs:__imp_EventWrite
0x140011cdc  mov     eax, 0Dh
0x140011ce1  jmp     loc_140011BE3
```
