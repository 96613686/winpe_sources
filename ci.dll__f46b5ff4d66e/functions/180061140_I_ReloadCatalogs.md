# I_ReloadCatalogs

- ea: `0x180061140`
- end: `0x180061393`
- name: `I_ReloadCatalogs`
- size: `595`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, PCUNICODE_STRING String1, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180096928`

## callees

- `0x180061140`
- `0x18008bc2c`
- `0x1800a1514`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180061362`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180061362`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061240`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800612a2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180061240`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800612a2`
- `ntoskrnl!EtwEventEnabled` at `0x180061180`
- `ntoskrnl!EtwEventEnabled` at `0x180061180`
- `ntoskrnl!IoGetActivityIdThread` at `0x180061190`
- `ntoskrnl!IoGetActivityIdThread` at `0x180061190`
- `ntoskrnl!EtwWrite` at `0x1800611b5`
- `ntoskrnl!EtwWrite` at `0x1800611b5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800611e8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061279`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800611e8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061279`

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
    v20 = (__int64 *)qword_180048780;
    if ( (__int64 *)qword_180048780 != &qword_180048780 )
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
      while ( v20 != &qword_180048780 );
    }
LABEL_28:
    ExReleasePushLockSharedEx(&g_CatalogStoreListLock, 0);
    goto LABEL_29;
  }
  v17 = I_ReloadCatalogDirectory(a1, a2, v16, a4, a5, a6, v15, v8);
  if ( v17 == -1073741766 )
  {
    ExAcquirePushLockSharedEx(&g_CatalogStoreListLock, 0);
    for ( i = (__int64 *)qword_180048780; i != &qword_180048780; i = (__int64 *)*i )
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
0x180061140  mov     rax, rsp
0x180061143  mov     [rax+18h], r8b
0x180061147  push    rbx
0x180061148  push    rbp
0x180061149  push    rsi
0x18006114a  push    rdi
0x18006114b  push    r12
0x18006114d  push    r13
0x18006114f  push    r14
0x180061151  push    r15
0x180061153  sub     rsp, 48h
0x180061157  mov     rdi, [rsp+88h+arg_38]
0x18006115f  mov     r15b, dl
0x180061162  mov     r12, rcx
0x180061165  lea     rdx, CiReloadCatalogsStart; EventDescriptor
0x18006116c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180061173  xor     r13d, r13d
0x180061176  mov     r14d, r9d
0x180061179  mov     [rax+18h], r13d
0x18006117d  mov     [rdi], r13d
0x180061180  call    cs:__imp_EtwEventEnabled
0x180061187  nop     dword ptr [rax+rax+00h]
0x18006118c  test    al, al
0x18006118e  jz      short loc_1800611C1
0x180061190  call    cs:__imp_IoGetActivityIdThread
0x180061197  nop     dword ptr [rax+rax+00h]
0x18006119c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800611a3  lea     rdx, CiReloadCatalogsStart; EventDescriptor
0x1800611aa  mov     r8, rax; ActivityId
0x1800611ad  mov     [rsp+88h+UserData], r13; UserData
0x1800611b2  xor     r9d, r9d; UserDataCount
0x1800611b5  call    cs:__imp_EtwWrite
0x1800611bc  nop     dword ptr [rax+rax+00h]
0x1800611c1  mov     rbx, [rsp+88h+String1]
0x1800611c9  test    rbx, rbx
0x1800611cc  jz      loc_180061296
0x1800611d2  lea     rdx, stru_18002EFE0; String2
0x1800611d9  cmp     rbx, rdx
0x1800611dc  jz      loc_180061296
0x1800611e2  mov     r8b, 1; CaseInSensitive
0x1800611e5  mov     rcx, rbx; String1
0x1800611e8  call    cs:__imp_RtlEqualUnicodeString
0x1800611ef  nop     dword ptr [rax+rax+00h]
0x1800611f4  test    al, al
0x1800611f6  jnz     loc_180061296
0x1800611fc  mov     eax, [rsp+88h+arg_28]
0x180061203  mov     r9d, r14d
0x180061206  mov     [rsp+88h+var_50], rdi
0x18006120b  mov     dl, r15b
0x18006120e  mov     [rsp+88h+var_58], rbx
0x180061213  mov     rcx, r12
0x180061216  mov     [rsp+88h+var_60], eax
0x18006121a  mov     eax, [rsp+88h+arg_20]
0x180061221  mov     dword ptr [rsp+88h+UserData], eax
0x180061225  call    I_ReloadCatalogDirectory
0x18006122a  mov     esi, eax
0x18006122c  cmp     eax, 0C000003Ah
0x180061231  jnz     loc_18006136E
0x180061237  xor     edx, edx
0x180061239  lea     rcx, g_CatalogStoreListLock
0x180061240  call    cs:__imp_ExAcquirePushLockSharedEx
0x180061247  nop     dword ptr [rax+rax+00h]
0x18006124c  mov     rdi, cs:qword_180048780
0x180061253  lea     rbp, qword_180048780
0x18006125a  cmp     rdi, rbp
0x18006125d  jz      loc_180061359
0x180061263  mov     eax, [rdi-18h]
0x180061266  test    al, 2
0x180061268  jz      short loc_180061289
0x18006126a  lea     rdx, [rdi-10h]; String2
0x18006126e  cmp     rbx, rdx
0x180061271  jz      short loc_18006128E
0x180061273  mov     r8b, 1; CaseInSensitive
0x180061276  mov     rcx, rbx; String1
0x180061279  call    cs:__imp_RtlEqualUnicodeString
0x180061280  nop     dword ptr [rax+rax+00h]
0x180061285  test    al, al
0x180061287  jnz     short loc_18006128E
0x180061289  mov     rdi, [rdi]
0x18006128c  jmp     short loc_18006125A
0x18006128e  mov     esi, r13d
0x180061291  jmp     loc_180061359
0x180061296  xor     edx, edx
0x180061298  lea     rcx, g_CatalogStoreListLock
0x18006129f  mov     esi, r13d
0x1800612a2  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800612a9  nop     dword ptr [rax+rax+00h]
0x1800612ae  mov     rbx, cs:qword_180048780
0x1800612b5  lea     rbp, qword_180048780
0x1800612bc  cmp     rbx, rbp
0x1800612bf  jz      loc_180061359
0x1800612c5  mov     r13d, [rsp+88h+arg_28]
0x1800612cd  mov     eax, [rbx-18h]
0x1800612d0  test    al, 4
0x1800612d2  jnz     short loc_18006134D
0x1800612d4  lea     rax, [rbx-10h]
0x1800612d8  mov     r9d, r14d
0x1800612db  lea     rcx, [rsp+88h+arg_10]
0x1800612e3  mov     dl, r15b
0x1800612e6  mov     [rsp+88h+var_50], rcx
0x1800612eb  mov     rcx, r12
0x1800612ee  mov     [rsp+88h+var_58], rax
0x1800612f3  mov     eax, [rsp+88h+arg_20]
0x1800612fa  mov     [rsp+88h+var_60], r13d
0x1800612ff  mov     dword ptr [rsp+88h+UserData], eax
0x180061303  call    I_ReloadCatalogDirectory
0x180061308  mov     ecx, eax
0x18006130a  test    eax, eax
0x18006130c  js      short loc_180061319
0x18006130e  mov     eax, [rsp+88h+arg_10]
0x180061315  or      [rdi], eax
0x180061317  jmp     short loc_18006134D
0x180061319  cmp     ecx, 0C000003Ah
0x18006131f  jnz     short loc_180061330
0x180061321  mov     eax, [rbx-18h]
0x180061324  test    al, 2
0x180061326  jz      short loc_180061330
0x180061328  or      eax, 4
0x18006132b  mov     [rbx-18h], eax
0x18006132e  jmp     short loc_18006134D
0x180061330  test    esi, esi
0x180061332  js      short loc_18006134D
0x180061334  mov     eax, [rbx-18h]
0x180061337  test    al, 1
0x180061339  jnz     short loc_18006134B
0x18006133b  cmp     ecx, 0C0000017h
0x180061341  jz      short loc_18006134B
0x180061343  cmp     ecx, 0C000009Ah
0x180061349  jnz     short loc_18006134D
0x18006134b  mov     esi, ecx
0x18006134d  mov     rbx, [rbx]
0x180061350  cmp     rbx, rbp
0x180061353  jnz     loc_1800612CD
0x180061359  xor     edx, edx
0x18006135b  lea     rcx, g_CatalogStoreListLock
0x180061362  call    cs:__imp_ExReleasePushLockSharedEx
0x180061369  nop     dword ptr [rax+rax+00h]
0x18006136e  xor     r8d, r8d
0x180061371  lea     rdx, CiReloadCatalogsComplete
0x180061378  mov     ecx, esi
0x18006137a  call    CiLogStatusEventWithCorrelationId
0x18006137f  mov     eax, esi
0x180061381  add     rsp, 48h
0x180061385  pop     r15
0x180061387  pop     r14
0x180061389  pop     r13
0x18006138b  pop     r12
0x18006138d  pop     rdi
0x18006138e  pop     rsi
0x18006138f  pop     rbp
0x180061390  pop     rbx
0x180061391  retn
```
