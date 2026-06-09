# SecHandleInterceptedVolsnapDeviceIoControl

- ea: `0x14003e638`
- end: `0x14003e8bf`
- name: `SecHandleInterceptedVolsnapDeviceIoControl`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14003e8c0`

## callees

- `0x140005f34`
- `0x140006218`
- `0x1400065e4`
- `0x140006754`
- `0x140006b6c`
- `0x14000885c`
- `0x140009b80`
- `0x140011650`
- `0x14003e4bc`
- `0x14003e638`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14003e703`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003e721`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003e703`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003e721`

## pseudocode

```c
void __fastcall SecHandleInterceptedVolsnapDeviceIoControl(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // r12
  __int64 v3; // rsi
  unsigned int v5; // edi
  PVOID *v6; // r14
  PVOID v7; // r14
  __int64 RequestorProcess; // rax
  unsigned int v9; // edx
  _WORD *v10; // rcx
  wchar_t *Str; // rdx
  int Next; // r10d
  struct _SLIST_ENTRY *v13; // r9
  __int64 v14; // r8
  int v15; // ecx
  unsigned int v16; // eax
  PVOID P; // [rsp+50h] [rbp-9h] BYREF
  PCUNICODE_STRING String1; // [rsp+58h] [rbp-1h]
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp+7h] BYREF
  PVOID v20; // [rsp+68h] [rbp+Fh]
  __int128 v21; // [rsp+70h] [rbp+17h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  String1 = 0;
  LOBYTE(v2) = 0;
  v20 = 0;
  v3 = 0;
  ListEntry = 0;
  v21 = 0;
  P = 0;
  v5 = *(_DWORD *)(v1 + 40);
  if ( (v5 != 5488696 || (dword_14001B728 & 1) == 0)
    && (v5 != 5488680 || (dword_14001B728 & 2) == 0)
    && (v5 != 5489048 || (dword_14001B728 & 4) == 0) )
  {
    return;
  }
  v6 = *(PVOID **)(*(_QWORD *)(v1 + 8) + 8LL);
  if ( (int)SecQueryObjectName(v6[1]) < 0
    || RtlCompareUnicodeString(String1, &s_volmgrDriverName, 1u)
    && RtlCompareUnicodeString(String1, &s_volsnapDriverName, 1u) )
  {
    goto LABEL_23;
  }
  if ( (int)SecQueryObjectName(v6) < 0 )
    goto LABEL_23;
  v7 = v20;
  RequestorProcess = SecFltGetRequestorProcess(a1);
  if ( (int)SecGetProcessContextByObject(RequestorProcess, &ListEntry) < 0 )
    goto LABEL_23;
  if ( v5 == 5488680 )
  {
    if ( *(_DWORD *)(v1 + 32) < 0x18u )
      goto LABEL_23;
    v2 = *(_QWORD *)(*(_QWORD *)(v1 + 48) + 16LL);
    goto LABEL_22;
  }
  if ( v5 != 5488696 )
  {
    if ( *(_DWORD *)(v1 + 32) < 0x14u )
      goto LABEL_23;
    v3 = *(_QWORD *)(v1 + 48) + 4LL;
    goto LABEL_22;
  }
  v9 = *(_DWORD *)(v1 + 32);
  if ( v9 < 4 || (v10 = *(_WORD **)(v1 + 48), v9 < (unsigned int)(unsigned __int16)*v10 + 2) )
  {
LABEL_23:
    if ( P )
      SecFreePool(P, 0x74736353u);
    goto LABEL_25;
  }
  *((_QWORD *)&v21 + 1) = v10 + 1;
  WORD1(v21) = *v10;
  LOWORD(v21) = WORD1(v21);
  if ( (int)SecUnicodeStringToString(&v21, &P) >= 0 )
  {
LABEL_22:
    Str = (wchar_t *)*((_QWORD *)v7 + 1);
    Next = (int)ListEntry[2].Next;
    v13 = ListEntry[3].Next;
    v14 = *((_QWORD *)&ListEntry[2].Next + 1);
    v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u) + 1;
    v16 = EventWriteDeviceIoControlForVolsnap(v15, Next, v14, (int)v13, v5 >> 2, Str, (wchar_t *)P, v2, v3);
    SecIncrementEtwCounters(v16);
    goto LABEL_23;
  }
  P = 0;
LABEL_25:
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v20 )
    SecFreePool(v20, 0x74736353u);
  if ( String1 )
    SecFreePool((PVOID)String1, 0x74736353u);
}

```

## disassembly

```asm
0x14003e638  mov     [rsp-8+arg_8], rbx
0x14003e63d  mov     [rsp-8+arg_10], rsi
0x14003e642  push    rbp
0x14003e643  push    rdi
0x14003e644  push    r12
0x14003e646  push    r14
0x14003e648  push    r15
0x14003e64a  lea     rbp, [rsp-37h]
0x14003e64f  sub     rsp, 90h
0x14003e656  mov     rax, cs:__security_cookie
0x14003e65d  xor     rax, rsp
0x14003e660  mov     [rbp+57h+var_30], rax
0x14003e664  mov     rbx, [rcx+10h]
0x14003e668  xorps   xmm0, xmm0
0x14003e66b  mov     [rbp+57h+String1], 0
0x14003e673  xor     r12d, r12d
0x14003e676  mov     [rbp+57h+var_48], 0
0x14003e67e  xor     esi, esi
0x14003e680  mov     [rbp+57h+ListEntry], 0
0x14003e688  mov     r15, rcx
0x14003e68b  movups  [rbp+57h+var_40], xmm0
0x14003e68f  mov     [rbp+57h+P], 0
0x14003e697  mov     edi, [rbx+28h]
0x14003e69a  cmp     edi, 53C038h
0x14003e6a0  jnz     short loc_14003E6AC
0x14003e6a2  mov     eax, cs:dword_14001B728
0x14003e6a8  test    al, 1
0x14003e6aa  jnz     short loc_14003E6D8
0x14003e6ac  cmp     edi, 53C028h
0x14003e6b2  jnz     short loc_14003E6BE
0x14003e6b4  mov     eax, cs:dword_14001B728
0x14003e6ba  test    al, 2
0x14003e6bc  jnz     short loc_14003E6D8
0x14003e6be  cmp     edi, 53C198h
0x14003e6c4  jnz     loc_14003E896
0x14003e6ca  mov     eax, cs:dword_14001B728
0x14003e6d0  test    al, 4
0x14003e6d2  jz      loc_14003E896
0x14003e6d8  mov     rax, [rbx+8]
0x14003e6dc  lea     rdx, [rbp+57h+String1]
0x14003e6e0  mov     r14, [rax+8]
0x14003e6e4  mov     rcx, [r14+8]; Object
0x14003e6e8  call    SecQueryObjectName
0x14003e6ed  test    eax, eax
0x14003e6ef  js      loc_14003E84F
0x14003e6f5  mov     rcx, [rbp+57h+String1]; String1
0x14003e6f9  lea     rdx, s_volmgrDriverName; String2
0x14003e700  mov     r8b, 1; CaseInSensitive
0x14003e703  call    cs:__imp_RtlCompareUnicodeString
0x14003e70a  nop     dword ptr [rax+rax+00h]
0x14003e70f  test    eax, eax
0x14003e711  jz      short loc_14003E735
0x14003e713  mov     rcx, [rbp+57h+String1]; String1
0x14003e717  lea     rdx, s_volsnapDriverName; String2
0x14003e71e  mov     r8b, 1; CaseInSensitive
0x14003e721  call    cs:__imp_RtlCompareUnicodeString
0x14003e728  nop     dword ptr [rax+rax+00h]
0x14003e72d  test    eax, eax
0x14003e72f  jnz     loc_14003E84F
0x14003e735  lea     rdx, [rbp+57h+var_48]
0x14003e739  mov     rcx, r14; Object
0x14003e73c  call    SecQueryObjectName
0x14003e741  test    eax, eax
0x14003e743  js      loc_14003E84F
0x14003e749  mov     r14, [rbp+57h+var_48]
0x14003e74d  mov     rcx, r15
0x14003e750  call    SecFltGetRequestorProcess
0x14003e755  mov     rcx, rax
0x14003e758  lea     rdx, [rbp+57h+ListEntry]
0x14003e75c  call    SecGetProcessContextByObject
0x14003e761  test    eax, eax
0x14003e763  js      loc_14003E84F
0x14003e769  mov     eax, edi
0x14003e76b  sub     eax, 53C028h
0x14003e770  jz      short loc_14003E7E1
0x14003e772  sub     eax, 10h
0x14003e775  jz      short loc_14003E796
0x14003e777  cmp     eax, 160h
0x14003e77c  jnz     loc_14003E84F
0x14003e782  cmp     dword ptr [rbx+20h], 14h
0x14003e786  jb      loc_14003E84F
0x14003e78c  mov     rsi, [rbx+30h]
0x14003e790  add     rsi, 4
0x14003e794  jmp     short loc_14003E7EF
0x14003e796  mov     edx, [rbx+20h]
0x14003e799  cmp     edx, 4
0x14003e79c  jb      loc_14003E84F
0x14003e7a2  mov     rcx, [rbx+30h]
0x14003e7a6  movzx   eax, word ptr [rcx]
0x14003e7a9  add     eax, 2
0x14003e7ac  cmp     edx, eax
0x14003e7ae  jb      loc_14003E84F
0x14003e7b4  lea     rax, [rcx+2]
0x14003e7b8  mov     qword ptr [rbp+57h+var_40+8], rax
0x14003e7bc  lea     rdx, [rbp+57h+P]
0x14003e7c0  movzx   eax, word ptr [rcx]
0x14003e7c3  lea     rcx, [rbp+57h+var_40]
0x14003e7c7  mov     word ptr [rbp+57h+var_40+2], ax
0x14003e7cb  mov     word ptr [rbp+57h+var_40], ax
0x14003e7cf  call    SecUnicodeStringToString
0x14003e7d4  test    eax, eax
0x14003e7d6  jns     short loc_14003E7EF
0x14003e7d8  mov     [rbp+57h+P], rsi
0x14003e7dc  jmp     loc_14003E862
0x14003e7e1  cmp     dword ptr [rbx+20h], 18h
0x14003e7e5  jb      short loc_14003E84F
0x14003e7e7  mov     rax, [rbx+30h]
0x14003e7eb  mov     r12, [rax+10h]
0x14003e7ef  mov     rax, [rbp+57h+ListEntry]
0x14003e7f3  mov     ecx, 1
0x14003e7f8  mov     rdx, [r14+8]
0x14003e7fc  shr     edi, 2
0x14003e7ff  and     edi, 0FFFh
0x14003e805  mov     r10d, [rax+20h]
0x14003e809  mov     r9, [rax+30h]; int
0x14003e80d  mov     r8, [rax+28h]; int
0x14003e811  mov     rax, cs:SecData
0x14003e818  lock xadd [rax+150h], rcx
0x14003e821  mov     rax, [rbp+57h+P]
0x14003e825  inc     rcx; int
0x14003e828  mov     [rsp+0B0h+var_70], rsi; __int64
0x14003e82d  mov     qword ptr [rsp+0B0h+var_78], r12; char
0x14003e832  mov     [rsp+0B0h+var_80], rax; wchar_t *
0x14003e837  mov     [rsp+0B0h+Str], rdx; Str
0x14003e83c  mov     edx, r10d; int
0x14003e83f  mov     dword ptr [rsp+0B0h+var_90], edi; char
0x14003e843  call    EventWriteDeviceIoControlForVolsnap
0x14003e848  mov     ecx, eax
0x14003e84a  call    SecIncrementEtwCounters
0x14003e84f  mov     rcx, [rbp+57h+P]; P
0x14003e853  test    rcx, rcx
0x14003e856  jz      short loc_14003E862
0x14003e858  mov     edx, 74736353h; Tag
0x14003e85d  call    SecFreePool
0x14003e862  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14003e866  test    rcx, rcx
0x14003e869  jz      short loc_14003E870
0x14003e86b  call    SecReleaseProcessContext
0x14003e870  mov     rcx, [rbp+57h+var_48]; P
0x14003e874  test    rcx, rcx
0x14003e877  jz      short loc_14003E883
0x14003e879  mov     edx, 74736353h; Tag
0x14003e87e  call    SecFreePool
0x14003e883  mov     rcx, [rbp+57h+String1]; P
0x14003e887  test    rcx, rcx
0x14003e88a  jz      short loc_14003E896
0x14003e88c  mov     edx, 74736353h; Tag
0x14003e891  call    SecFreePool
0x14003e896  mov     rcx, [rbp+57h+var_30]
0x14003e89a  xor     rcx, rsp; StackCookie
0x14003e89d  call    __security_check_cookie
0x14003e8a2  lea     r11, [rsp+0B0h+var_20]
0x14003e8aa  mov     rbx, [r11+38h]
0x14003e8ae  mov     rsi, [r11+40h]
0x14003e8b2  mov     rsp, r11
0x14003e8b5  pop     r15
0x14003e8b7  pop     r14
0x14003e8b9  pop     r12
0x14003e8bb  pop     rdi
0x14003e8bc  pop     rbp
0x14003e8bd  retn
```
