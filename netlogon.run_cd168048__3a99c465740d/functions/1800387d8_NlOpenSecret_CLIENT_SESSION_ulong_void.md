# NlOpenSecret(_CLIENT_SESSION *,ulong,void * *)

- ea: `0x1800387d8`
- end: `0x18003893c`
- name: `?NlOpenSecret@@YAJPEAU_CLIENT_SESSION@@KPEAPEAX@Z`
- size: `356`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006a94`
- `0x18003ad18`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x1800387d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800388c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800388c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800388ac`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800388ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038881`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038881`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038920`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038920`
- `LSASRV!LsarOpenSecret` at `0x18003890a`
- `LSASRV!LsarOpenSecret` at `0x18003890a`
- `ntdll!RtlInitUnicodeString` at `0x1800388e5`
- `ntdll!RtlInitUnicodeString` at `0x1800388e5`

## string_xrefs

- `0x180038808`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003883a`: `NlOpenSecret: Invalid account type\n`

## pseudocode

```c
__int64 __fastcall NlOpenSecret(struct _CLIENT_SESSION *a1, unsigned int a2, void **a3, char *a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rsi
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  const WCHAR *v13; // rdx
  unsigned int v14; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  DestinationString = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x97u,
      a4);
  if ( *((_DWORD *)a1 + 70) != 2
    && (*((_DWORD *)a1 + 70) == 3 || *((_DWORD *)a1 + 70) == 4 || (unsigned int)(*((_DWORD *)a1 + 70) - 6) >= 2) )
  {
    NlPrintRoutine(0x100u, L"NlOpenSecret: Invalid account type\n");
    return 3221225701LL;
  }
  if ( (*((_DWORD *)a1 + 73) & 0x20000) != 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*((_QWORD *)a1 + 25) + 2 * v8) );
    v9 = (unsigned int)(v8 + 44);
    v10 = (unsigned int)v9;
    v11 = (WCHAR *)LocalAlloc(0, 2 * v9);
    v12 = v11;
    if ( !v11 )
      return 3221225495LL;
    _o_wcscpy_s(v11, v10, L"_SC_{262E99C9-6160-4871-ACEC-4E61736B6F21}_");
    _o_wcscat_s(v12, v10, *((_QWORD *)a1 + 25));
    v13 = v12;
  }
  else
  {
    v12 = 0;
    v13 = L"$MACHINE.ACC";
  }
  RtlInitUnicodeString(&DestinationString, v13);
  v14 = LsarOpenSecret(*(_QWORD *)(*((_QWORD *)a1 + 34) + 392LL), &DestinationString, a2, a3);
  if ( v12 )
    LocalFree(v12);
  return v14;
}

```

## disassembly

```asm
0x1800387d8  push    rbx
0x1800387da  push    rbp
0x1800387db  push    rsi
0x1800387dc  push    rdi
0x1800387dd  push    r14
0x1800387df  push    r15
0x1800387e1  sub     rsp, 38h
0x1800387e5  xor     r15d, r15d
0x1800387e8  xorps   xmm0, xmm0
0x1800387eb  mov     rbp, r8
0x1800387ee  mov     r14d, edx
0x1800387f1  mov     rbx, rcx
0x1800387f4  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800387f9  cmp     [rcx+148h], r15d
0x180038800  ja      short loc_18003881B
0x180038802  mov     r8d, 97h; unsigned int
0x180038808  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003880f  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180038816  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003881b  mov     ecx, [rbx+118h]
0x180038821  sub     ecx, 2
0x180038824  jz      short loc_180038855
0x180038826  sub     ecx, 1
0x180038829  jz      short loc_18003883A
0x18003882b  sub     ecx, 1
0x18003882e  jz      short loc_18003883A
0x180038830  sub     ecx, 2
0x180038833  jz      short loc_180038855
0x180038835  cmp     ecx, 1
0x180038838  jz      short loc_180038855
0x18003883a  lea     rdx, aNlopensecretIn; "NlOpenSecret: Invalid account type\n"
0x180038841  mov     ecx, 100h; unsigned int
0x180038846  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003884b  mov     eax, 0C00000E5h
0x180038850  jmp     loc_18003892E
0x180038855  test    dword ptr [rbx+124h], 20000h
0x18003885f  jz      short loc_1800388D6
0x180038861  mov     rcx, [rbx+0C8h]
0x180038868  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003886c  inc     rax
0x18003886f  cmp     [rcx+rax*2], r15w
0x180038874  jnz     short loc_18003886C
0x180038876  add     eax, 2Ch ; ','
0x180038879  xor     ecx, ecx; uFlags
0x18003887b  mov     esi, eax
0x18003887d  lea     rdx, [rax+rax]; uBytes
0x180038881  call    cs:__imp_LocalAlloc
0x180038888  nop     dword ptr [rax+rax+00h]
0x18003888d  mov     rdi, rax
0x180038890  test    rax, rax
0x180038893  jnz     short loc_18003889F
0x180038895  mov     eax, 0C0000017h
0x18003889a  jmp     loc_18003892E
0x18003889f  lea     r8, aSc262e99c96160; "_SC_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x1800388a6  mov     rdx, rsi
0x1800388a9  mov     rcx, rdi
0x1800388ac  call    cs:__imp__o_wcscpy_s
0x1800388b3  nop     dword ptr [rax+rax+00h]
0x1800388b8  mov     r8, [rbx+0C8h]
0x1800388bf  mov     rdx, rsi
0x1800388c2  mov     rcx, rdi
0x1800388c5  call    cs:__imp__o_wcscat_s
0x1800388cc  nop     dword ptr [rax+rax+00h]
0x1800388d1  mov     rdx, rdi
0x1800388d4  jmp     short loc_1800388E0
0x1800388d6  mov     rdi, r15
0x1800388d9  lea     rdx, aMachineAcc; "$MACHINE.ACC"
0x1800388e0  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800388e5  call    cs:__imp_RtlInitUnicodeString
0x1800388ec  nop     dword ptr [rax+rax+00h]
0x1800388f1  mov     rcx, [rbx+110h]
0x1800388f8  lea     rdx, [rsp+68h+DestinationString]
0x1800388fd  mov     r9, rbp
0x180038900  mov     r8d, r14d
0x180038903  mov     rcx, [rcx+188h]
0x18003890a  call    cs:__imp_LsarOpenSecret
0x180038911  nop     dword ptr [rax+rax+00h]
0x180038916  mov     ebx, eax
0x180038918  test    rdi, rdi
0x18003891b  jz      short loc_18003892C
0x18003891d  mov     rcx, rdi; hMem
0x180038920  call    cs:__imp_LocalFree
0x180038927  nop     dword ptr [rax+rax+00h]
0x18003892c  mov     eax, ebx
0x18003892e  add     rsp, 38h
0x180038932  pop     r15
0x180038934  pop     r14
0x180038936  pop     rdi
0x180038937  pop     rsi
0x180038938  pop     rbp
0x180038939  pop     rbx
0x18003893a  retn
```
