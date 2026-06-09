# EfspCheckForNetSession

- ea: `0x1800076b4`
- end: `0x180007808`
- name: `EfspCheckForNetSession`
- size: `340`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800055b0`
- `0x1800058a0`
- `0x180005bc0`
- `0x1800063c0`
- `0x180006710`
- `0x180006a00`
- `0x180006bb0`
- `0x180006df0`
- `0x180007810`

## callees

- `0x1800076b4`
- `0x18000c3c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800077ac`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800077ac`
- `ntdll!NtQueryInformationToken` at `0x180007732`
- `ntdll!NtQueryInformationToken` at `0x180007782`
- `ntdll!NtQueryInformationToken` at `0x180007732`
- `ntdll!NtQueryInformationToken` at `0x180007782`
- `ntdll!RtlAllocateHeap` at `0x18000775b`
- `ntdll!RtlAllocateHeap` at `0x18000775b`
- `ntdll!RtlFreeHeap` at `0x1800077d3`
- `ntdll!RtlFreeHeap` at `0x1800077d3`
- `ntdll!NtClose` at `0x1800077e3`
- `ntdll!NtClose` at `0x1800077e3`
- `ntdll!NtOpenThreadToken` at `0x180007705`
- `ntdll!NtOpenThreadToken` at `0x180007705`

## pseudocode

```c
__int64 EfspCheckForNetSession()
{
  unsigned int v0; // esi
  NTSTATUS v1; // eax
  PVOID Heap; // rbx
  int *v3; // r14
  int v4; // edi
  ULONG TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE TokenInformation[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 1;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle) >= 0 )
  {
    v1 = NtQueryInformationToken(TokenHandle, TokenGroups, TokenInformation, 0x400u, &TokenInformationLength);
    if ( v1 >= 0 )
    {
      Heap = 0;
      v3 = (int *)TokenInformation;
    }
    else
    {
      if ( v1 != -1073741789 )
        goto LABEL_14;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
      if ( !Heap )
        goto LABEL_14;
      if ( NtQueryInformationToken(TokenHandle, TokenGroups, Heap, TokenInformationLength, &TokenInformationLength) < 0 )
      {
LABEL_13:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        goto LABEL_14;
      }
      v3 = (int *)Heap;
    }
    v4 = *v3;
    while ( --v4 >= 0 )
    {
      if ( IsWellKnownSid(*(PSID *)&v3[4 * v4 + 2], WinNetworkSid) )
        goto LABEL_12;
    }
    v0 = 0;
LABEL_12:
    if ( Heap )
      goto LABEL_13;
  }
LABEL_14:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800076b4  push    rbp
0x1800076b6  push    rbx
0x1800076b7  push    rsi
0x1800076b8  push    rdi
0x1800076b9  push    r14
0x1800076bb  lea     rbp, [rsp-350h]
0x1800076c3  sub     rsp, 450h
0x1800076ca  mov     rax, cs:__security_cookie
0x1800076d1  xor     rax, rsp
0x1800076d4  mov     [rbp+370h+var_30], rax
0x1800076db  mov     esi, 1
0x1800076e0  mov     [rsp+470h+TokenHandle], 0
0x1800076e9  lea     r9, [rsp+470h+TokenHandle]; TokenHandle
0x1800076ee  mov     [rsp+470h+TokenInformationLength], 0
0x1800076f6  mov     r8b, sil; OpenAsSelf
0x1800076f9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180007700  lea     ebx, [rsi+7]
0x180007703  mov     edx, ebx; DesiredAccess
0x180007705  call    cs:__imp_NtOpenThreadToken
0x18000770b  test    eax, eax
0x18000770d  js      loc_1800077D9
0x180007713  mov     rcx, [rsp+470h+TokenHandle]; TokenHandle
0x180007718  lea     rax, [rsp+470h+TokenInformationLength]
0x18000771d  lea     edi, [rsi+1]
0x180007720  mov     [rsp+470h+ReturnLength], rax; ReturnLength
0x180007725  mov     edx, edi; TokenInformationClass
0x180007727  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x18000772c  mov     r9d, 400h; TokenInformationLength
0x180007732  call    cs:__imp_NtQueryInformationToken
0x180007738  test    eax, eax
0x18000773a  jns     short loc_180007791
0x18000773c  cmp     eax, 0C0000023h
0x180007741  jnz     loc_1800077D9
0x180007747  mov     rcx, gs:60h
0x180007750  mov     edx, ebx; Flags
0x180007752  mov     r8d, [rsp+470h+TokenInformationLength]; Size
0x180007757  mov     rcx, [rcx+30h]; HeapHandle
0x18000775b  call    cs:__imp_RtlAllocateHeap
0x180007761  mov     rbx, rax
0x180007764  test    rax, rax
0x180007767  jz      short loc_1800077D9
0x180007769  mov     r9d, [rsp+470h+TokenInformationLength]; TokenInformationLength
0x18000776e  lea     rax, [rsp+470h+TokenInformationLength]
0x180007773  mov     rcx, [rsp+470h+TokenHandle]; TokenHandle
0x180007778  mov     r8, rbx; TokenInformation
0x18000777b  mov     edx, edi; TokenInformationClass
0x18000777d  mov     [rsp+470h+ReturnLength], rax; ReturnLength
0x180007782  call    cs:__imp_NtQueryInformationToken
0x180007788  test    eax, eax
0x18000778a  js      short loc_1800077C1
0x18000778c  mov     r14, rbx
0x18000778f  jmp     short loc_180007798
0x180007791  xor     ebx, ebx
0x180007793  lea     r14, [rsp+470h+TokenInformation]
0x180007798  mov     edi, [r14]
0x18000779b  jmp     short loc_1800077B6
0x18000779d  mov     ecx, edi
0x18000779f  mov     edx, 9; WellKnownSidType
0x1800077a4  add     rcx, rcx
0x1800077a7  mov     rcx, [r14+rcx*8+8]; pSid
0x1800077ac  call    cs:__imp_IsWellKnownSid
0x1800077b2  test    eax, eax
0x1800077b4  jnz     short loc_1800077BC
0x1800077b6  sub     edi, esi
0x1800077b8  jns     short loc_18000779D
0x1800077ba  xor     esi, esi
0x1800077bc  test    rbx, rbx
0x1800077bf  jz      short loc_1800077D9
0x1800077c1  mov     rcx, gs:60h
0x1800077ca  mov     r8, rbx; P
0x1800077cd  xor     edx, edx; Flags
0x1800077cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800077d3  call    cs:__imp_RtlFreeHeap
0x1800077d9  mov     rcx, [rsp+470h+TokenHandle]; Handle
0x1800077de  test    rcx, rcx
0x1800077e1  jz      short loc_1800077E9
0x1800077e3  call    cs:__imp_NtClose
0x1800077e9  mov     eax, esi
0x1800077eb  mov     rcx, [rbp+370h+var_30]
0x1800077f2  xor     rcx, rsp; StackCookie
0x1800077f5  call    __security_check_cookie
0x1800077fa  add     rsp, 450h
0x180007801  pop     r14
0x180007803  pop     rdi
0x180007804  pop     rsi
0x180007805  pop     rbx
0x180007806  pop     rbp
0x180007807  retn
```
