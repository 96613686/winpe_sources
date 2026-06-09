# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800ae884`
- end: `0x1800aea4a`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `454`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ae644`

## callees

- `0x1800059a8`
- `0x1800ae36c`
- `0x1800ae884`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800ae9ed`
- `ntdll!RtlCompareUnicodeString` at `0x1800ae9ed`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ae8e7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ae982`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ae8e7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ae982`
- `ntdll!RtlAllocateHeap` at `0x1800ae929`
- `ntdll!RtlAllocateHeap` at `0x1800ae929`
- `ntdll!RtlInitUnicodeString` at `0x1800ae9bc`
- `ntdll!RtlInitUnicodeString` at `0x1800ae9bc`
- `ntdll!NtQueryInformationToken` at `0x1800ae8c4`
- `ntdll!NtQueryInformationToken` at `0x1800ae970`
- `ntdll!NtQueryInformationToken` at `0x1800ae8c4`
- `ntdll!NtQueryInformationToken` at `0x1800ae970`

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
  _DWORD *v10; // rdi
  int v11; // eax
  ULONG v12; // ebx
  _DWORD *v13; // rsi
  __int64 v14; // rbx
  const UNICODE_STRING *v15; // rbp
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+40h] [rbp-38h]
  ULONG Size; // [rsp+98h] [rbp+20h] BYREF
  int Size_4; // [rsp+9Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(Size, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (Size * (unsigned __int128)0x10uLL) >> 64, 16LL * Size),
          (v10 = Heap) != 0) )
    {
      memset_0(Heap, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 >= 0 )
      {
        v13 = v10 + 1;
        if ( v10[1]
          && (DestinationString = 0, RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID"), v14 = 0, v17 = 0, *v13) )
        {
          while ( 1 )
          {
            v15 = (const UNICODE_STRING *)(*((_QWORD *)v10 + 1) + 40 * v14);
            if ( !RtlCompareUnicodeString(&DestinationString, v15, 1u) )
              break;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= *v13 )
              goto LABEL_13;
          }
          *a3 = v15;
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
    else
    {
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
      return 8;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1800ae884  mov     rax, rsp
0x1800ae887  mov     [rax+8], rbx
0x1800ae88b  mov     [rax+10h], rbp
0x1800ae88f  mov     [rax+20h], r9
0x1800ae893  push    rsi
0x1800ae894  push    rdi
0x1800ae895  push    r12
0x1800ae897  push    r14
0x1800ae899  push    r15
0x1800ae89b  sub     rsp, 50h
0x1800ae89f  xor     r9d, r9d; TokenInformationLength
0x1800ae8a2  mov     dword ptr [rax+20h], 0
0x1800ae8a9  mov     r15, r8
0x1800ae8ac  lea     rax, [rax+20h]
0x1800ae8b0  mov     r12, rdx
0x1800ae8b3  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800ae8b8  xor     r8d, r8d; TokenInformation
0x1800ae8bb  mov     rbx, rcx
0x1800ae8be  lea     esi, [r9+27h]
0x1800ae8c2  mov     edx, esi; TokenInformationClass
0x1800ae8c4  call    cs:__imp_NtQueryInformationToken
0x1800ae8cb  nop     dword ptr [rax+rax+00h]
0x1800ae8d0  cmp     eax, 0C0000023h
0x1800ae8d5  jz      short loc_1800AE8F8
0x1800ae8d7  test    eax, eax
0x1800ae8d9  jnz     short loc_1800AE8E5
0x1800ae8db  mov     eax, 54Fh
0x1800ae8e0  jmp     loc_1800AEA30
0x1800ae8e5  mov     ecx, eax; Status
0x1800ae8e7  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800ae8ee  nop     dword ptr [rax+rax+00h]
0x1800ae8f3  jmp     loc_1800AEA30
0x1800ae8f8  mov     ecx, dword ptr [rsp+78h+Size]
0x1800ae8ff  mov     eax, 10h
0x1800ae904  mul     rcx
0x1800ae907  mov     qword ptr [rsp+78h+DestinationString.Length], 0
0x1800ae910  test    rdx, rdx
0x1800ae913  jnz     loc_1800AEA24
0x1800ae919  mov     rcx, gs:60h
0x1800ae922  mov     r8, rax; Size
0x1800ae925  mov     rcx, [rcx+30h]; HeapHandle
0x1800ae929  call    cs:__imp_RtlAllocateHeap
0x1800ae930  nop     dword ptr [rax+rax+00h]
0x1800ae935  mov     rdi, rax
0x1800ae938  test    rax, rax
0x1800ae93b  jz      loc_1800AEA24
0x1800ae941  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x1800ae949  xor     edx, edx; Val
0x1800ae94b  mov     rcx, rax; void *
0x1800ae94e  call    memset_0
0x1800ae953  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x1800ae95b  lea     rax, [rsp+78h+Size]
0x1800ae963  mov     r8, rdi; TokenInformation
0x1800ae966  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800ae96b  mov     edx, esi; TokenInformationClass
0x1800ae96d  mov     rcx, rbx; TokenHandle
0x1800ae970  call    cs:__imp_NtQueryInformationToken
0x1800ae977  nop     dword ptr [rax+rax+00h]
0x1800ae97c  test    eax, eax
0x1800ae97e  jns     short loc_1800AE99F
0x1800ae980  mov     ecx, eax; Status
0x1800ae982  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800ae989  nop     dword ptr [rax+rax+00h]
0x1800ae98e  mov     rcx, rdi; P
0x1800ae991  mov     ebx, eax
0x1800ae993  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800ae998  mov     eax, ebx
0x1800ae99a  jmp     loc_1800AEA30
0x1800ae99f  lea     rsi, [rdi+4]
0x1800ae9a3  cmp     dword ptr [rsi], 0
0x1800ae9a6  jbe     short loc_1800AEA03
0x1800ae9a8  xorps   xmm0, xmm0
0x1800ae9ab  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800ae9b2  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800ae9b7  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1800ae9bc  call    cs:__imp_RtlInitUnicodeString
0x1800ae9c3  nop     dword ptr [rax+rax+00h]
0x1800ae9c8  xor     ebx, ebx
0x1800ae9ca  xorps   xmm0, xmm0
0x1800ae9cd  movups  [rsp+78h+var_38], xmm0
0x1800ae9d2  cmp     [rsi], ebx
0x1800ae9d4  jbe     short loc_1800AEA03
0x1800ae9d6  mov     rax, [rdi+8]
0x1800ae9da  lea     rcx, [rbx+rbx*4]
0x1800ae9de  mov     r8b, 1; CaseInsensitive
0x1800ae9e1  lea     rbp, [rax+rcx*8]
0x1800ae9e5  mov     rdx, rbp; String2
0x1800ae9e8  lea     rcx, [rsp+78h+DestinationString]; String1
0x1800ae9ed  call    cs:__imp_RtlCompareUnicodeString
0x1800ae9f4  nop     dword ptr [rax+rax+00h]
0x1800ae9f9  test    eax, eax
0x1800ae9fb  jz      short loc_1800AEA12
0x1800ae9fd  inc     ebx
0x1800ae9ff  cmp     ebx, [rsi]
0x1800aea01  jb      short loc_1800AE9D6
0x1800aea03  mov     rcx, rdi; P
0x1800aea06  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800aea0b  mov     eax, 490h
0x1800aea10  jmp     short loc_1800AEA30
0x1800aea12  mov     [r15], rbp
0x1800aea15  xor     ecx, ecx; P
0x1800aea17  mov     [r12], rdi
0x1800aea1b  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800aea20  xor     eax, eax
0x1800aea22  jmp     short loc_1800AEA30
0x1800aea24  xor     ecx, ecx; P
0x1800aea26  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800aea2b  mov     eax, 8
0x1800aea30  lea     r11, [rsp+78h+var_28]
0x1800aea35  mov     rbx, [r11+30h]
0x1800aea39  mov     rbp, [r11+38h]
0x1800aea3d  mov     rsp, r11
0x1800aea40  pop     r15
0x1800aea42  pop     r14
0x1800aea44  pop     r12
0x1800aea46  pop     rdi
0x1800aea47  pop     rsi
0x1800aea48  retn
```
