# NfsUpCallpPasswdGroupValidatePasswdInfoForDuplicates

- ea: `0x140011cec`
- end: `0x140011e7a`
- name: `NfsUpCallpPasswdGroupValidatePasswdInfoForDuplicates`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140011800`

## callees

- `0x140011cec`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140011e6a`
- `ADVAPI32!EventWrite` at `0x140011e6a`
- `ADVAPI32!EventEnabled` at `0x140011df0`
- `ADVAPI32!EventEnabled` at `0x140011e48`
- `ADVAPI32!EventEnabled` at `0x140011df0`
- `ADVAPI32!EventEnabled` at `0x140011e48`
- `ntdll!RtlCompareUnicodeString` at `0x140011d64`
- `ntdll!RtlCompareUnicodeString` at `0x140011d64`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupValidatePasswdInfoForDuplicates(__int64 a1, __int64 *a2, __int64 a3)
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
    if ( *(_DWORD *)(*(_QWORD *)(v7 + 8 * v8) + 16LL) == *(_DWORD *)(*(_QWORD *)(v7 + 8 * v9) + 16LL) )
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
      UserData.Ptr = *((_QWORD *)v15 + 1);
      v16 = -1;
      UserData.Size = v14;
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
  UserData.Ptr = *(_QWORD *)(v7 + 8 * v8) + 16LL;
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
0x140011cec  push    rbp
0x140011cee  push    rbx
0x140011cef  push    rsi
0x140011cf0  push    rdi
0x140011cf1  push    r14
0x140011cf3  push    r15
0x140011cf5  mov     rbp, rsp
0x140011cf8  sub     rsp, 68h
0x140011cfc  mov     rax, cs:__security_cookie
0x140011d03  xor     rax, rsp
0x140011d06  mov     [rbp+var_18], rax
0x140011d0a  mov     eax, [rdx+18h]
0x140011d0d  mov     rdi, r8
0x140011d10  mov     rbx, rdx
0x140011d13  cmp     eax, 2
0x140011d16  jb      short loc_140011D79
0x140011d18  lea     edx, [rax-1]
0x140011d1b  xor     r15d, r15d
0x140011d1e  test    edx, edx
0x140011d20  jz      short loc_140011D79
0x140011d22  mov     r10, [rbx+8]
0x140011d26  mov     eax, r15d
0x140011d29  mov     r8, [r10+rax*8]
0x140011d2d  lea     r9d, [rax+1]
0x140011d31  mov     rcx, [r10+r9*8]
0x140011d35  add     r8, 10h
0x140011d39  mov     eax, [rcx+10h]
0x140011d3c  cmp     [r8], eax
0x140011d3f  jz      loc_140011E09
0x140011d45  mov     eax, r9d
0x140011d48  cmp     r9d, edx
0x140011d4b  jb      short loc_140011D29
0x140011d4d  mov     edx, r15d
0x140011d50  mov     rcx, [rbx]
0x140011d53  lea     esi, [rdx+1]
0x140011d56  mov     r14d, edx
0x140011d59  mov     r8b, 1; CaseInsensitive
0x140011d5c  mov     rdx, [rcx+rsi*8]; String2
0x140011d60  mov     rcx, [rcx+r14*8]; String1
0x140011d64  call    cs:__imp_RtlCompareUnicodeString
0x140011d6a  test    eax, eax
0x140011d6c  jz      short loc_140011D94
0x140011d6e  mov     eax, [rbx+18h]
0x140011d71  mov     edx, esi
0x140011d73  dec     eax
0x140011d75  cmp     esi, eax
0x140011d77  jb      short loc_140011D50
0x140011d79  xor     eax, eax
0x140011d7b  mov     rcx, [rbp+var_18]
0x140011d7f  xor     rcx, rsp; StackCookie
0x140011d82  call    __security_check_cookie
0x140011d87  add     rsp, 68h
0x140011d8b  pop     r15
0x140011d8d  pop     r14
0x140011d8f  pop     rdi
0x140011d90  pop     rsi
0x140011d91  pop     rbx
0x140011d92  pop     rbp
0x140011d93  retn
0x140011d94  mov     rcx, [rbx]
0x140011d97  mov     rax, [rcx+r14*8]
0x140011d9b  mov     [rbp+UserData.Ptr], rax
0x140011d9f  mov     qword ptr [rbp+UserData.Size], 2
0x140011da7  mov     rax, [rcx+r14*8]
0x140011dab  movzx   ecx, word ptr [rax]
0x140011dae  mov     rax, [rax+8]
0x140011db2  mov     [rbp+UserData.Ptr], rax
0x140011db6  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011dba  mov     [rbp+UserData.Size], ecx
0x140011dbd  mov     [rbp+var_28], rdi
0x140011dc1  inc     rax
0x140011dc4  cmp     [rdi+rax*2], r15w
0x140011dc9  jnz     short loc_140011DC1
0x140011dcb  mov     rcx, cs:RegHandle; RegHandle
0x140011dd2  lea     eax, ds:2[rax*2]
0x140011dd9  mov     [rbp+var_20], eax
0x140011ddc  mov     [rbp+var_1C], r15d
0x140011de0  test    rcx, rcx
0x140011de3  jz      loc_140011E70
0x140011de9  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_NAME_IN_FILE; EventDescriptor
0x140011df0  call    cs:__imp_EventEnabled
0x140011df6  test    al, al
0x140011df8  jz      short loc_140011E70
0x140011dfa  mov     r8d, 3
0x140011e00  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_NAME_IN_FILE
0x140011e07  jmp     short loc_140011E5F
0x140011e09  mov     [rbp+UserData.Ptr], r8
0x140011e0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011e11  mov     qword ptr [rbp+UserData.Size], 4
0x140011e19  mov     [rbp+var_38], rdi
0x140011e1d  inc     rax
0x140011e20  cmp     [rdi+rax*2], r15w
0x140011e25  jnz     short loc_140011E1D
0x140011e27  mov     rcx, cs:RegHandle; RegHandle
0x140011e2e  lea     eax, ds:2[rax*2]
0x140011e35  mov     [rbp+var_30], eax
0x140011e38  mov     [rbp+var_2C], r15d
0x140011e3c  test    rcx, rcx
0x140011e3f  jz      short loc_140011E70
0x140011e41  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_ID_IN_FILE; EventDescriptor
0x140011e48  call    cs:__imp_EventEnabled
0x140011e4e  test    al, al
0x140011e50  jz      short loc_140011E70
0x140011e52  mov     r8d, 2; UserDataCount
0x140011e58  lea     rdx, EVENT_NFS_SERVICE_DUPLICATE_ID_IN_FILE; EventDescriptor
0x140011e5f  mov     rcx, cs:RegHandle; RegHandle
0x140011e66  lea     r9, [rbp+UserData]; UserData
0x140011e6a  call    cs:__imp_EventWrite
0x140011e70  mov     eax, 0Dh
0x140011e75  jmp     loc_140011D7B
```
