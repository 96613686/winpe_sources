# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800ad3cc`
- end: `0x1800ad585`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `441`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ad1ac`

## callees

- `0x180006158`
- `0x1800ace34`
- `0x1800ad3cc`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800ad52a`
- `ntdll!RtlCompareUnicodeString` at `0x1800ad52a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ad429`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ad4c1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ad429`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ad4c1`
- `ntdll!RtlAllocateHeap` at `0x1800ad468`
- `ntdll!RtlAllocateHeap` at `0x1800ad468`
- `ntdll!RtlInitUnicodeString` at `0x1800ad4f8`
- `ntdll!RtlInitUnicodeString` at `0x1800ad4f8`
- `ntdll!NtQueryInformationToken` at `0x1800ad406`
- `ntdll!NtQueryInformationToken` at `0x1800ad4af`
- `ntdll!NtQueryInformationToken` at `0x1800ad406`
- `ntdll!NtQueryInformationToken` at `0x1800ad4af`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        const UNICODE_STRING **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID Heap; // rax
  PVOID v10; // rdi
  int v11; // eax
  ULONG v12; // ebx
  __int64 v13; // rbx
  const UNICODE_STRING *v14; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v16; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 != -1073741789 )
  {
    if ( v7 )
      return RtlNtStatusToDosErrorNoTeb(v7);
    else
      return 1359;
  }
  *(_QWORD *)&DestinationString.Length = 0;
  if ( !is_mul_ok(Size, 0x10u) )
  {
    v10 = 0;
    goto LABEL_16;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (Size * (unsigned __int128)0x10uLL) >> 64, 16LL * Size);
  v10 = Heap;
  if ( !Heap )
  {
LABEL_16:
    ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
    return 8;
  }
  memset_0(Heap, 0, Size);
  v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
  if ( v11 >= 0 )
  {
    if ( *((_DWORD *)v10 + 1)
      && (DestinationString = 0,
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID"),
          v13 = 0,
          v16 = 0,
          *((_DWORD *)v10 + 1)) )
    {
      while ( 1 )
      {
        v14 = (const UNICODE_STRING *)(*((_QWORD *)v10 + 1) + 40 * v13);
        if ( !RtlCompareUnicodeString(&DestinationString, v14, 1u) )
          break;
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= *((_DWORD *)v10 + 1) )
          goto LABEL_13;
      }
      *a3 = v14;
      *a2 = v10;
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
      return 0;
    }
    else
    {
LABEL_13:
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
      return 1168;
    }
  }
  else
  {
    v12 = RtlNtStatusToDosErrorNoTeb(v11);
    ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
    return v12;
  }
}

```

## disassembly

```asm
0x1800ad3cc  mov     rax, rsp
0x1800ad3cf  mov     [rax+8], rbx
0x1800ad3d3  mov     [rax+10h], rsi
0x1800ad3d7  mov     [rax+20h], r9
0x1800ad3db  push    rdi
0x1800ad3dc  push    r14
0x1800ad3de  push    r15
0x1800ad3e0  sub     rsp, 50h
0x1800ad3e4  and     dword ptr [rax+20h], 0
0x1800ad3e8  lea     rax, [rax+20h]
0x1800ad3ec  xor     r9d, r9d; TokenInformationLength
0x1800ad3ef  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800ad3f4  mov     r14, r8
0x1800ad3f7  mov     r15, rdx
0x1800ad3fa  xor     r8d, r8d; TokenInformation
0x1800ad3fd  mov     rbx, rcx
0x1800ad400  lea     esi, [r9+27h]
0x1800ad404  mov     edx, esi; TokenInformationClass
0x1800ad406  call    cs:__imp_NtQueryInformationToken
0x1800ad40d  nop     dword ptr [rax+rax+00h]
0x1800ad412  cmp     eax, 0C0000023h
0x1800ad417  jz      short loc_1800AD43A
0x1800ad419  test    eax, eax
0x1800ad41b  jnz     short loc_1800AD427
0x1800ad41d  mov     eax, 54Fh
0x1800ad422  jmp     loc_1800AD570
0x1800ad427  mov     ecx, eax; Status
0x1800ad429  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800ad430  nop     dword ptr [rax+rax+00h]
0x1800ad435  jmp     loc_1800AD570
0x1800ad43a  mov     ecx, dword ptr [rsp+68h+Size]
0x1800ad441  mov     eax, 10h
0x1800ad446  and     qword ptr [rsp+68h+DestinationString.Length], 0
0x1800ad44c  mul     rcx
0x1800ad44f  test    rdx, rdx
0x1800ad452  jnz     loc_1800AD561
0x1800ad458  mov     rcx, gs:60h
0x1800ad461  mov     r8, rax; Size
0x1800ad464  mov     rcx, [rcx+30h]; HeapHandle
0x1800ad468  call    cs:__imp_RtlAllocateHeap
0x1800ad46f  nop     dword ptr [rax+rax+00h]
0x1800ad474  mov     rdi, rax
0x1800ad477  test    rax, rax
0x1800ad47a  jz      loc_1800AD563
0x1800ad480  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800ad488  xor     edx, edx; Val
0x1800ad48a  mov     rcx, rax; void *
0x1800ad48d  call    memset_0
0x1800ad492  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800ad49a  lea     rax, [rsp+68h+Size]
0x1800ad4a2  mov     r8, rdi; TokenInformation
0x1800ad4a5  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800ad4aa  mov     edx, esi; TokenInformationClass
0x1800ad4ac  mov     rcx, rbx; TokenHandle
0x1800ad4af  call    cs:__imp_NtQueryInformationToken
0x1800ad4b6  nop     dword ptr [rax+rax+00h]
0x1800ad4bb  test    eax, eax
0x1800ad4bd  jns     short loc_1800AD4DE
0x1800ad4bf  mov     ecx, eax; Status
0x1800ad4c1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800ad4c8  nop     dword ptr [rax+rax+00h]
0x1800ad4cd  mov     rcx, rdi; P
0x1800ad4d0  mov     ebx, eax
0x1800ad4d2  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800ad4d7  mov     eax, ebx
0x1800ad4d9  jmp     loc_1800AD570
0x1800ad4de  cmp     dword ptr [rdi+4], 0
0x1800ad4e2  jbe     short loc_1800AD541
0x1800ad4e4  xorps   xmm0, xmm0
0x1800ad4e7  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800ad4ee  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800ad4f3  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800ad4f8  call    cs:__imp_RtlInitUnicodeString
0x1800ad4ff  nop     dword ptr [rax+rax+00h]
0x1800ad504  xor     ebx, ebx
0x1800ad506  xorps   xmm0, xmm0
0x1800ad509  movups  [rsp+68h+var_28], xmm0
0x1800ad50e  cmp     [rdi+4], ebx
0x1800ad511  jbe     short loc_1800AD541
0x1800ad513  mov     rax, [rdi+8]
0x1800ad517  lea     rcx, [rbx+rbx*4]
0x1800ad51b  mov     r8b, 1; CaseInsensitive
0x1800ad51e  lea     rsi, [rax+rcx*8]
0x1800ad522  mov     rdx, rsi; String2
0x1800ad525  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800ad52a  call    cs:__imp_RtlCompareUnicodeString
0x1800ad531  nop     dword ptr [rax+rax+00h]
0x1800ad536  test    eax, eax
0x1800ad538  jz      short loc_1800AD550
0x1800ad53a  inc     ebx
0x1800ad53c  cmp     ebx, [rdi+4]
0x1800ad53f  jb      short loc_1800AD513
0x1800ad541  mov     rcx, rdi; P
0x1800ad544  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800ad549  mov     eax, 490h
0x1800ad54e  jmp     short loc_1800AD570
0x1800ad550  mov     [r14], rsi
0x1800ad553  xor     ecx, ecx; P
0x1800ad555  mov     [r15], rdi
0x1800ad558  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800ad55d  xor     eax, eax
0x1800ad55f  jmp     short loc_1800AD570
0x1800ad561  xor     edi, edi
0x1800ad563  mov     rcx, rdi; P
0x1800ad566  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800ad56b  mov     eax, 8
0x1800ad570  mov     rbx, [rsp+68h+arg_0]
0x1800ad575  mov     rsi, [rsp+68h+arg_8]
0x1800ad57a  add     rsp, 50h
0x1800ad57e  pop     r15
0x1800ad580  pop     r14
0x1800ad582  pop     rdi
0x1800ad583  retn
```
