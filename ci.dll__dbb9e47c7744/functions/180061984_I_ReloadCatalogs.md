# I_ReloadCatalogs

- ea: `0x180061984`
- end: `0x180061bd7`
- name: `I_ReloadCatalogs`
- size: `595`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, PCUNICODE_STRING String1, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180097f58`

## callees

- `0x180061984`
- `0x18008d25c`
- `0x1800a2b44`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180061ba6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180061ba6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061a84`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061ae6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061a84`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061ae6`
- `ntoskrnl!EtwEventEnabled` at `0x1800619c4`
- `ntoskrnl!EtwEventEnabled` at `0x1800619c4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800619d4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800619d4`
- `ntoskrnl!EtwWrite` at `0x1800619f9`
- `ntoskrnl!EtwWrite` at `0x1800619f9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061a2c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061abd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061a2c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061abd`

## pseudocode

```c
__int64 __fastcall I_ReloadCatalogs(
        int a1,
        char a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        UNICODE_STRING *String1,
        _DWORD *a8)
{
  _DWORD *v8; // rdi
  REGHANDLE v11; // rcx
  __int64 v13; // rcx
  const GUID *ActivityIdThread; // rax
  UNICODE_STRING *v15; // rbx
  __int64 v16; // r8
  int v17; // esi
  __int64 *i; // rdi
  __int64 v19; // r8
  __int64 *v20; // rbx
  int v21; // r13d
  int v22; // ecx
  int v23; // eax
  int v25; // [rsp+A0h] [rbp+18h] BYREF

  v8 = a8;
  v11 = g_EtwEventHandle;
  v25 = 0;
  *a8 = 0;
  if ( EtwEventEnabled(v11, &CiReloadCatalogsStart) )
  {
    ActivityIdThread = (const GUID *)IoGetActivityIdThread(v13);
    EtwWrite(g_EtwEventHandle, &CiReloadCatalogsStart, ActivityIdThread, 0, 0);
  }
  v15 = String1;
  if ( !String1 || String1 == &stru_18002EFE0 || RtlEqualUnicodeString(String1, &stru_18002EFE0, 1u) )
  {
    v17 = 0;
    ExAcquirePushLockSharedEx(&g_CatalogStoreListLock, 0);
    v20 = (__int64 *)qword_180049780;
    if ( (__int64 *)qword_180049780 != &qword_180049780 )
    {
      v21 = a6;
      do
      {
        if ( (*(_DWORD *)(v20 - 3) & 4) == 0 )
        {
          v22 = I_ReloadCatalogDirectory(a1, a2, v19, a4, a5, v21, (UNICODE_STRING *)v20 - 1, &v25);
          if ( v22 < 0 )
          {
            if ( v22 == -1073741766 && (v23 = *((_DWORD *)v20 - 6), (v23 & 2) != 0) )
            {
              *((_DWORD *)v20 - 6) = v23 | 4;
            }
            else if ( v17 >= 0 && ((*(_DWORD *)(v20 - 3) & 1) != 0 || v22 == -1073741801 || v22 == -1073741670) )
            {
              v17 = v22;
            }
          }
          else
          {
            *v8 |= v25;
          }
        }
        v20 = (__int64 *)*v20;
      }
      while ( v20 != &qword_180049780 );
    }
LABEL_28:
    ExReleasePushLockSharedEx(&g_CatalogStoreListLock, 0);
    goto LABEL_29;
  }
  v17 = I_ReloadCatalogDirectory(a1, a2, v16, a4, a5, a6, v15, v8);
  if ( v17 == -1073741766 )
  {
    ExAcquirePushLockSharedEx(&g_CatalogStoreListLock, 0);
    for ( i = (__int64 *)qword_180049780; i != &qword_180049780; i = (__int64 *)*i )
    {
      if ( (*(_DWORD *)(i - 3) & 2) != 0
        && (v15 == (UNICODE_STRING *)(i - 2) || RtlEqualUnicodeString(v15, (PCUNICODE_STRING)i - 1, 1u)) )
      {
        v17 = 0;
        goto LABEL_28;
      }
    }
    goto LABEL_28;
  }
LABEL_29:
  CiLogStatusEventWithCorrelationId(v17, (const EVENT_DESCRIPTOR *)CiReloadCatalogsComplete, 0);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180061984  mov     rax, rsp
0x180061987  mov     [rax+18h], r8b
0x18006198b  push    rbx
0x18006198c  push    rbp
0x18006198d  push    rsi
0x18006198e  push    rdi
0x18006198f  push    r12
0x180061991  push    r13
0x180061993  push    r14
0x180061995  push    r15
0x180061997  sub     rsp, 48h
0x18006199b  mov     rdi, [rsp+88h+arg_38]
0x1800619a3  mov     r15b, dl
0x1800619a6  mov     r12, rcx
0x1800619a9  lea     rdx, CiReloadCatalogsStart; EventDescriptor
0x1800619b0  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800619b7  xor     r13d, r13d
0x1800619ba  mov     r14d, r9d
0x1800619bd  mov     [rax+18h], r13d
0x1800619c1  mov     [rdi], r13d
0x1800619c4  call    cs:__imp_EtwEventEnabled
0x1800619cb  nop     dword ptr [rax+rax+00h]
0x1800619d0  test    al, al
0x1800619d2  jz      short loc_180061A05
0x1800619d4  call    cs:__imp_IoGetActivityIdThread
0x1800619db  nop     dword ptr [rax+rax+00h]
0x1800619e0  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800619e7  lea     rdx, CiReloadCatalogsStart; EventDescriptor
0x1800619ee  mov     r8, rax; ActivityId
0x1800619f1  mov     [rsp+88h+UserData], r13; UserData
0x1800619f6  xor     r9d, r9d; UserDataCount
0x1800619f9  call    cs:__imp_EtwWrite
0x180061a00  nop     dword ptr [rax+rax+00h]
0x180061a05  mov     rbx, [rsp+88h+String1]
0x180061a0d  test    rbx, rbx
0x180061a10  jz      loc_180061ADA
0x180061a16  lea     rdx, stru_18002EFE0; String2
0x180061a1d  cmp     rbx, rdx
0x180061a20  jz      loc_180061ADA
0x180061a26  mov     r8b, 1; CaseInSensitive
0x180061a29  mov     rcx, rbx; String1
0x180061a2c  call    cs:__imp_RtlEqualUnicodeString
0x180061a33  nop     dword ptr [rax+rax+00h]
0x180061a38  test    al, al
0x180061a3a  jnz     loc_180061ADA
0x180061a40  mov     eax, [rsp+88h+arg_28]
0x180061a47  mov     r9d, r14d
0x180061a4a  mov     [rsp+88h+var_50], rdi
0x180061a4f  mov     dl, r15b
0x180061a52  mov     [rsp+88h+var_58], rbx
0x180061a57  mov     rcx, r12
0x180061a5a  mov     [rsp+88h+var_60], eax
0x180061a5e  mov     eax, [rsp+88h+arg_20]
0x180061a65  mov     dword ptr [rsp+88h+UserData], eax
0x180061a69  call    I_ReloadCatalogDirectory
0x180061a6e  mov     esi, eax
0x180061a70  cmp     eax, 0C000003Ah
0x180061a75  jnz     loc_180061BB2
0x180061a7b  xor     edx, edx
0x180061a7d  lea     rcx, g_CatalogStoreListLock
0x180061a84  call    cs:__imp_ExAcquirePushLockSharedEx
0x180061a8b  nop     dword ptr [rax+rax+00h]
0x180061a90  mov     rdi, cs:qword_180049780
0x180061a97  lea     rbp, qword_180049780
0x180061a9e  cmp     rdi, rbp
0x180061aa1  jz      loc_180061B9D
0x180061aa7  mov     eax, [rdi-18h]
0x180061aaa  test    al, 2
0x180061aac  jz      short loc_180061ACD
0x180061aae  lea     rdx, [rdi-10h]; String2
0x180061ab2  cmp     rbx, rdx
0x180061ab5  jz      short loc_180061AD2
0x180061ab7  mov     r8b, 1; CaseInSensitive
0x180061aba  mov     rcx, rbx; String1
0x180061abd  call    cs:__imp_RtlEqualUnicodeString
0x180061ac4  nop     dword ptr [rax+rax+00h]
0x180061ac9  test    al, al
0x180061acb  jnz     short loc_180061AD2
0x180061acd  mov     rdi, [rdi]
0x180061ad0  jmp     short loc_180061A9E
0x180061ad2  mov     esi, r13d
0x180061ad5  jmp     loc_180061B9D
0x180061ada  xor     edx, edx
0x180061adc  lea     rcx, g_CatalogStoreListLock
0x180061ae3  mov     esi, r13d
0x180061ae6  call    cs:__imp_ExAcquirePushLockSharedEx
0x180061aed  nop     dword ptr [rax+rax+00h]
0x180061af2  mov     rbx, cs:qword_180049780
0x180061af9  lea     rbp, qword_180049780
0x180061b00  cmp     rbx, rbp
0x180061b03  jz      loc_180061B9D
0x180061b09  mov     r13d, [rsp+88h+arg_28]
0x180061b11  mov     eax, [rbx-18h]
0x180061b14  test    al, 4
0x180061b16  jnz     short loc_180061B91
0x180061b18  lea     rax, [rbx-10h]
0x180061b1c  mov     r9d, r14d
0x180061b1f  lea     rcx, [rsp+88h+arg_10]
0x180061b27  mov     dl, r15b
0x180061b2a  mov     [rsp+88h+var_50], rcx
0x180061b2f  mov     rcx, r12
0x180061b32  mov     [rsp+88h+var_58], rax
0x180061b37  mov     eax, [rsp+88h+arg_20]
0x180061b3e  mov     [rsp+88h+var_60], r13d
0x180061b43  mov     dword ptr [rsp+88h+UserData], eax
0x180061b47  call    I_ReloadCatalogDirectory
0x180061b4c  mov     ecx, eax
0x180061b4e  test    eax, eax
0x180061b50  js      short loc_180061B5D
0x180061b52  mov     eax, [rsp+88h+arg_10]
0x180061b59  or      [rdi], eax
0x180061b5b  jmp     short loc_180061B91
0x180061b5d  cmp     ecx, 0C000003Ah
0x180061b63  jnz     short loc_180061B74
0x180061b65  mov     eax, [rbx-18h]
0x180061b68  test    al, 2
0x180061b6a  jz      short loc_180061B74
0x180061b6c  or      eax, 4
0x180061b6f  mov     [rbx-18h], eax
0x180061b72  jmp     short loc_180061B91
0x180061b74  test    esi, esi
0x180061b76  js      short loc_180061B91
0x180061b78  mov     eax, [rbx-18h]
0x180061b7b  test    al, 1
0x180061b7d  jnz     short loc_180061B8F
0x180061b7f  cmp     ecx, 0C0000017h
0x180061b85  jz      short loc_180061B8F
0x180061b87  cmp     ecx, 0C000009Ah
0x180061b8d  jnz     short loc_180061B91
0x180061b8f  mov     esi, ecx
0x180061b91  mov     rbx, [rbx]
0x180061b94  cmp     rbx, rbp
0x180061b97  jnz     loc_180061B11
0x180061b9d  xor     edx, edx
0x180061b9f  lea     rcx, g_CatalogStoreListLock
0x180061ba6  call    cs:__imp_ExReleasePushLockSharedEx
0x180061bad  nop     dword ptr [rax+rax+00h]
0x180061bb2  xor     r8d, r8d
0x180061bb5  lea     rdx, CiReloadCatalogsComplete
0x180061bbc  mov     ecx, esi
0x180061bbe  call    CiLogStatusEventWithCorrelationId
0x180061bc3  mov     eax, esi
0x180061bc5  add     rsp, 48h
0x180061bc9  pop     r15
0x180061bcb  pop     r14
0x180061bcd  pop     r13
0x180061bcf  pop     r12
0x180061bd1  pop     rdi
0x180061bd2  pop     rsi
0x180061bd3  pop     rbp
0x180061bd4  pop     rbx
0x180061bd5  retn
```
