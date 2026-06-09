# NlOpenSecret(_CLIENT_SESSION *,ulong,void * *)

- ea: `0x1800366e8`
- end: `0x180036824`
- name: `?NlOpenSecret@@YAJPEAU_CLIENT_SESSION@@KPEAPEAX@Z`
- size: `316`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006860`
- `0x180038ad0`

## callees

- `0x180007278`
- `0x18000d710`
- `0x1800366e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800367c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800367c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800367b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800367b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036791`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003680f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003680f`
- `LSASRV!LsarOpenSecret` at `0x1800367ff`
- `LSASRV!LsarOpenSecret` at `0x1800367ff`
- `ntdll!RtlInitUnicodeString` at `0x1800367e0`
- `ntdll!RtlInitUnicodeString` at `0x1800367e0`

## string_xrefs

- `0x180036718`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003674a`: `NlOpenSecret: Invalid account type\n`

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
      151,
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
    _o_wcscpy_s(v11, v10);
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
0x1800366e8  push    rbx
0x1800366ea  push    rbp
0x1800366eb  push    rsi
0x1800366ec  push    rdi
0x1800366ed  push    r14
0x1800366ef  push    r15
0x1800366f1  sub     rsp, 38h
0x1800366f5  xor     r15d, r15d
0x1800366f8  xorps   xmm0, xmm0
0x1800366fb  mov     rbp, r8
0x1800366fe  mov     r14d, edx
0x180036701  mov     rbx, rcx
0x180036704  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180036709  cmp     [rcx+148h], r15d
0x180036710  ja      short loc_18003672B
0x180036712  mov     r8d, 97h; unsigned int
0x180036718  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18003671f  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180036726  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003672b  mov     ecx, [rbx+118h]
0x180036731  sub     ecx, 2
0x180036734  jz      short loc_180036765
0x180036736  sub     ecx, 1
0x180036739  jz      short loc_18003674A
0x18003673b  sub     ecx, 1
0x18003673e  jz      short loc_18003674A
0x180036740  sub     ecx, 2
0x180036743  jz      short loc_180036765
0x180036745  cmp     ecx, 1
0x180036748  jz      short loc_180036765
0x18003674a  lea     rdx, aNlopensecretIn; "NlOpenSecret: Invalid account type\n"
0x180036751  mov     ecx, 100h; unsigned int
0x180036756  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003675b  mov     eax, 0C00000E5h
0x180036760  jmp     loc_180036817
0x180036765  test    dword ptr [rbx+124h], 20000h
0x18003676f  jz      short loc_1800367D1
0x180036771  mov     rcx, [rbx+0C8h]
0x180036778  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003677c  inc     rax
0x18003677f  cmp     [rcx+rax*2], r15w
0x180036784  jnz     short loc_18003677C
0x180036786  add     eax, 2Ch ; ','
0x180036789  xor     ecx, ecx; uFlags
0x18003678b  mov     esi, eax
0x18003678d  lea     rdx, [rax+rax]; uBytes
0x180036791  call    cs:__imp_LocalAlloc
0x180036797  mov     rdi, rax
0x18003679a  test    rax, rax
0x18003679d  jnz     short loc_1800367A6
0x18003679f  mov     eax, 0C0000017h
0x1800367a4  jmp     short loc_180036817
0x1800367a6  lea     r8, aSc262e99c96160; "_SC_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x1800367ad  mov     rdx, rsi
0x1800367b0  mov     rcx, rdi
0x1800367b3  call    cs:__imp__o_wcscpy_s
0x1800367b9  mov     r8, [rbx+0C8h]
0x1800367c0  mov     rdx, rsi
0x1800367c3  mov     rcx, rdi
0x1800367c6  call    cs:__imp__o_wcscat_s
0x1800367cc  mov     rdx, rdi
0x1800367cf  jmp     short loc_1800367DB
0x1800367d1  mov     rdi, r15
0x1800367d4  lea     rdx, aMachineAcc; "$MACHINE.ACC"
0x1800367db  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800367e0  call    cs:__imp_RtlInitUnicodeString
0x1800367e6  mov     rcx, [rbx+110h]
0x1800367ed  lea     rdx, [rsp+68h+DestinationString]
0x1800367f2  mov     r9, rbp
0x1800367f5  mov     r8d, r14d
0x1800367f8  mov     rcx, [rcx+188h]
0x1800367ff  call    cs:__imp_LsarOpenSecret
0x180036805  mov     ebx, eax
0x180036807  test    rdi, rdi
0x18003680a  jz      short loc_180036815
0x18003680c  mov     rcx, rdi; hMem
0x18003680f  call    cs:__imp_LocalFree
0x180036815  mov     eax, ebx
0x180036817  add     rsp, 38h
0x18003681b  pop     r15
0x18003681d  pop     r14
0x18003681f  pop     rdi
0x180036820  pop     rsi
0x180036821  pop     rbp
0x180036822  pop     rbx
0x180036823  retn
```
