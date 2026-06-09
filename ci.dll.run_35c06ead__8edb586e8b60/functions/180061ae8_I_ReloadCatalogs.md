# I_ReloadCatalogs

- ea: `0x180061ae8`
- end: `0x180061d3b`
- name: `I_ReloadCatalogs`
- size: `595`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, PCUNICODE_STRING String1, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008e728`

## callees

- `0x180061ae8`
- `0x18008bd4c`
- `0x18009257c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180061d0a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180061d0a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061be8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061c4a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061be8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061c4a`
- `ntoskrnl!EtwEventEnabled` at `0x180061b28`
- `ntoskrnl!EtwEventEnabled` at `0x180061b28`
- `ntoskrnl!IoGetActivityIdThread` at `0x180061b38`
- `ntoskrnl!IoGetActivityIdThread` at `0x180061b38`
- `ntoskrnl!EtwWrite` at `0x180061b5d`
- `ntoskrnl!EtwWrite` at `0x180061b5d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061b90`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061c21`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061b90`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061c21`

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
  if ( !String1 || String1 == &stru_18002E470 || RtlEqualUnicodeString(String1, &stru_18002E470, 1u) )
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
0x180061ae8  mov     rax, rsp
0x180061aeb  mov     [rax+18h], r8b
0x180061aef  push    rbx
0x180061af0  push    rbp
0x180061af1  push    rsi
0x180061af2  push    rdi
0x180061af3  push    r12
0x180061af5  push    r13
0x180061af7  push    r14
0x180061af9  push    r15
0x180061afb  sub     rsp, 48h
0x180061aff  mov     rdi, [rsp+88h+arg_38]
0x180061b07  mov     r15b, dl
0x180061b0a  mov     r12, rcx
0x180061b0d  lea     rdx, CiReloadCatalogsStart; EventDescriptor
0x180061b14  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180061b1b  xor     r13d, r13d
0x180061b1e  mov     r14d, r9d
0x180061b21  mov     [rax+18h], r13d
0x180061b25  mov     [rdi], r13d
0x180061b28  call    cs:__imp_EtwEventEnabled
0x180061b2f  nop     dword ptr [rax+rax+00h]
0x180061b34  test    al, al
0x180061b36  jz      short loc_180061B69
0x180061b38  call    cs:__imp_IoGetActivityIdThread
0x180061b3f  nop     dword ptr [rax+rax+00h]
0x180061b44  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180061b4b  lea     rdx, CiReloadCatalogsStart; EventDescriptor
0x180061b52  mov     r8, rax; ActivityId
0x180061b55  mov     [rsp+88h+UserData], r13; UserData
0x180061b5a  xor     r9d, r9d; UserDataCount
0x180061b5d  call    cs:__imp_EtwWrite
0x180061b64  nop     dword ptr [rax+rax+00h]
0x180061b69  mov     rbx, [rsp+88h+String1]
0x180061b71  test    rbx, rbx
0x180061b74  jz      loc_180061C3E
0x180061b7a  lea     rdx, stru_18002E470; String2
0x180061b81  cmp     rbx, rdx
0x180061b84  jz      loc_180061C3E
0x180061b8a  mov     r8b, 1; CaseInSensitive
0x180061b8d  mov     rcx, rbx; String1
0x180061b90  call    cs:__imp_RtlEqualUnicodeString
0x180061b97  nop     dword ptr [rax+rax+00h]
0x180061b9c  test    al, al
0x180061b9e  jnz     loc_180061C3E
0x180061ba4  mov     eax, [rsp+88h+arg_28]
0x180061bab  mov     r9d, r14d
0x180061bae  mov     [rsp+88h+var_50], rdi
0x180061bb3  mov     dl, r15b
0x180061bb6  mov     [rsp+88h+var_58], rbx
0x180061bbb  mov     rcx, r12
0x180061bbe  mov     [rsp+88h+var_60], eax
0x180061bc2  mov     eax, [rsp+88h+arg_20]
0x180061bc9  mov     dword ptr [rsp+88h+UserData], eax
0x180061bcd  call    I_ReloadCatalogDirectory
0x180061bd2  mov     esi, eax
0x180061bd4  cmp     eax, 0C000003Ah
0x180061bd9  jnz     loc_180061D16
0x180061bdf  xor     edx, edx
0x180061be1  lea     rcx, g_CatalogStoreListLock
0x180061be8  call    cs:__imp_ExAcquirePushLockSharedEx
0x180061bef  nop     dword ptr [rax+rax+00h]
0x180061bf4  mov     rdi, cs:qword_180049780
0x180061bfb  lea     rbp, qword_180049780
0x180061c02  cmp     rdi, rbp
0x180061c05  jz      loc_180061D01
0x180061c0b  mov     eax, [rdi-18h]
0x180061c0e  test    al, 2
0x180061c10  jz      short loc_180061C31
0x180061c12  lea     rdx, [rdi-10h]; String2
0x180061c16  cmp     rbx, rdx
0x180061c19  jz      short loc_180061C36
0x180061c1b  mov     r8b, 1; CaseInSensitive
0x180061c1e  mov     rcx, rbx; String1
0x180061c21  call    cs:__imp_RtlEqualUnicodeString
0x180061c28  nop     dword ptr [rax+rax+00h]
0x180061c2d  test    al, al
0x180061c2f  jnz     short loc_180061C36
0x180061c31  mov     rdi, [rdi]
0x180061c34  jmp     short loc_180061C02
0x180061c36  mov     esi, r13d
0x180061c39  jmp     loc_180061D01
0x180061c3e  xor     edx, edx
0x180061c40  lea     rcx, g_CatalogStoreListLock
0x180061c47  mov     esi, r13d
0x180061c4a  call    cs:__imp_ExAcquirePushLockSharedEx
0x180061c51  nop     dword ptr [rax+rax+00h]
0x180061c56  mov     rbx, cs:qword_180049780
0x180061c5d  lea     rbp, qword_180049780
0x180061c64  cmp     rbx, rbp
0x180061c67  jz      loc_180061D01
0x180061c6d  mov     r13d, [rsp+88h+arg_28]
0x180061c75  mov     eax, [rbx-18h]
0x180061c78  test    al, 4
0x180061c7a  jnz     short loc_180061CF5
0x180061c7c  lea     rax, [rbx-10h]
0x180061c80  mov     r9d, r14d
0x180061c83  lea     rcx, [rsp+88h+arg_10]
0x180061c8b  mov     dl, r15b
0x180061c8e  mov     [rsp+88h+var_50], rcx
0x180061c93  mov     rcx, r12
0x180061c96  mov     [rsp+88h+var_58], rax
0x180061c9b  mov     eax, [rsp+88h+arg_20]
0x180061ca2  mov     [rsp+88h+var_60], r13d
0x180061ca7  mov     dword ptr [rsp+88h+UserData], eax
0x180061cab  call    I_ReloadCatalogDirectory
0x180061cb0  mov     ecx, eax
0x180061cb2  test    eax, eax
0x180061cb4  js      short loc_180061CC1
0x180061cb6  mov     eax, [rsp+88h+arg_10]
0x180061cbd  or      [rdi], eax
0x180061cbf  jmp     short loc_180061CF5
0x180061cc1  cmp     ecx, 0C000003Ah
0x180061cc7  jnz     short loc_180061CD8
0x180061cc9  mov     eax, [rbx-18h]
0x180061ccc  test    al, 2
0x180061cce  jz      short loc_180061CD8
0x180061cd0  or      eax, 4
0x180061cd3  mov     [rbx-18h], eax
0x180061cd6  jmp     short loc_180061CF5
0x180061cd8  test    esi, esi
0x180061cda  js      short loc_180061CF5
0x180061cdc  mov     eax, [rbx-18h]
0x180061cdf  test    al, 1
0x180061ce1  jnz     short loc_180061CF3
0x180061ce3  cmp     ecx, 0C0000017h
0x180061ce9  jz      short loc_180061CF3
0x180061ceb  cmp     ecx, 0C000009Ah
0x180061cf1  jnz     short loc_180061CF5
0x180061cf3  mov     esi, ecx
0x180061cf5  mov     rbx, [rbx]
0x180061cf8  cmp     rbx, rbp
0x180061cfb  jnz     loc_180061C75
0x180061d01  xor     edx, edx
0x180061d03  lea     rcx, g_CatalogStoreListLock
0x180061d0a  call    cs:__imp_ExReleasePushLockSharedEx
0x180061d11  nop     dword ptr [rax+rax+00h]
0x180061d16  xor     r8d, r8d
0x180061d19  lea     rdx, CiReloadCatalogsComplete
0x180061d20  mov     ecx, esi
0x180061d22  call    CiLogStatusEventWithCorrelationId
0x180061d27  mov     eax, esi
0x180061d29  add     rsp, 48h
0x180061d2d  pop     r15
0x180061d2f  pop     r14
0x180061d31  pop     r13
0x180061d33  pop     r12
0x180061d35  pop     rdi
0x180061d36  pop     rsi
0x180061d37  pop     rbp
0x180061d38  pop     rbx
0x180061d39  retn
```
