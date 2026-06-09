# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180038a08`
- end: `0x180038ba3`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `411`
- prototype: `ULONG __fastcall(HANDLE TokenHandle, _QWORD *, const UNICODE_STRING **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800385e8`

## callees

- `0x180003474`
- `0x180037fa0`
- `0x180038a08`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180038a48`
- `ntdll!NtQueryInformationToken` at `0x180038ae2`
- `ntdll!NtQueryInformationToken` at `0x180038a48`
- `ntdll!NtQueryInformationToken` at `0x180038ae2`
- `ntdll!RtlInitUnicodeString` at `0x180038b22`
- `ntdll!RtlInitUnicodeString` at `0x180038b22`
- `ntdll!RtlCompareUnicodeString` at `0x180038b4d`
- `ntdll!RtlCompareUnicodeString` at `0x180038b4d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180038a65`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180038aee`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180038a65`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180038aee`
- `ntdll!RtlAllocateHeap` at `0x180038aa1`
- `ntdll!RtlAllocateHeap` at `0x180038aa1`

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
0x180038a08  mov     rax, rsp
0x180038a0b  mov     [rax+8], rbx
0x180038a0f  mov     [rax+10h], rbp
0x180038a13  mov     [rax+20h], r9
0x180038a17  push    rsi
0x180038a18  push    rdi
0x180038a19  push    r12
0x180038a1b  push    r14
0x180038a1d  push    r15
0x180038a1f  sub     rsp, 50h
0x180038a23  xor     r9d, r9d; TokenInformationLength
0x180038a26  mov     dword ptr [rax+20h], 0
0x180038a2d  mov     r15, r8
0x180038a30  lea     rax, [rax+20h]
0x180038a34  mov     r12, rdx
0x180038a37  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180038a3c  xor     r8d, r8d; TokenInformation
0x180038a3f  mov     rbx, rcx
0x180038a42  lea     esi, [r9+27h]
0x180038a46  mov     edx, esi; TokenInformationClass
0x180038a48  call    cs:__imp_NtQueryInformationToken
0x180038a4e  cmp     eax, 0C0000023h
0x180038a53  jz      short loc_180038A70
0x180038a55  test    eax, eax
0x180038a57  jnz     short loc_180038A63
0x180038a59  mov     eax, 54Fh
0x180038a5e  jmp     loc_180038B8A
0x180038a63  mov     ecx, eax; Status
0x180038a65  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180038a6b  jmp     loc_180038B8A
0x180038a70  mov     ecx, dword ptr [rsp+78h+Size]
0x180038a77  mov     eax, 10h
0x180038a7c  mul     rcx
0x180038a7f  mov     qword ptr [rsp+78h+DestinationString.Length], 0
0x180038a88  test    rdx, rdx
0x180038a8b  jnz     loc_180038B7E
0x180038a91  mov     rcx, gs:60h
0x180038a9a  mov     r8, rax; Size
0x180038a9d  mov     rcx, [rcx+30h]; HeapHandle
0x180038aa1  call    cs:__imp_RtlAllocateHeap
0x180038aa7  mov     rdi, rax
0x180038aaa  test    rax, rax
0x180038aad  jz      loc_180038B7E
0x180038ab3  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180038abb  xor     edx, edx; Val
0x180038abd  mov     rcx, rax; void *
0x180038ac0  call    memset_0
0x180038ac5  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x180038acd  lea     rax, [rsp+78h+Size]
0x180038ad5  mov     r8, rdi; TokenInformation
0x180038ad8  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180038add  mov     edx, esi; TokenInformationClass
0x180038adf  mov     rcx, rbx; TokenHandle
0x180038ae2  call    cs:__imp_NtQueryInformationToken
0x180038ae8  test    eax, eax
0x180038aea  jns     short loc_180038B05
0x180038aec  mov     ecx, eax; Status
0x180038aee  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180038af4  mov     rcx, rdi; P
0x180038af7  mov     ebx, eax
0x180038af9  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180038afe  mov     eax, ebx
0x180038b00  jmp     loc_180038B8A
0x180038b05  lea     rsi, [rdi+4]
0x180038b09  cmp     dword ptr [rsi], 0
0x180038b0c  jbe     short loc_180038B5D
0x180038b0e  xorps   xmm0, xmm0
0x180038b11  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180038b18  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180038b1d  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180038b22  call    cs:__imp_RtlInitUnicodeString
0x180038b28  xor     ebx, ebx
0x180038b2a  xorps   xmm0, xmm0
0x180038b2d  movups  [rsp+78h+var_38], xmm0
0x180038b32  cmp     [rsi], ebx
0x180038b34  jbe     short loc_180038B5D
0x180038b36  mov     rax, [rdi+8]
0x180038b3a  lea     rcx, [rbx+rbx*4]
0x180038b3e  mov     r8b, 1; CaseInsensitive
0x180038b41  lea     rbp, [rax+rcx*8]
0x180038b45  mov     rdx, rbp; String2
0x180038b48  lea     rcx, [rsp+78h+DestinationString]; String1
0x180038b4d  call    cs:__imp_RtlCompareUnicodeString
0x180038b53  test    eax, eax
0x180038b55  jz      short loc_180038B6C
0x180038b57  inc     ebx
0x180038b59  cmp     ebx, [rsi]
0x180038b5b  jb      short loc_180038B36
0x180038b5d  mov     rcx, rdi; P
0x180038b60  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180038b65  mov     eax, 490h
0x180038b6a  jmp     short loc_180038B8A
0x180038b6c  mov     [r15], rbp
0x180038b6f  xor     ecx, ecx; P
0x180038b71  mov     [r12], rdi
0x180038b75  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180038b7a  xor     eax, eax
0x180038b7c  jmp     short loc_180038B8A
0x180038b7e  xor     ecx, ecx; P
0x180038b80  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180038b85  mov     eax, 8
0x180038b8a  lea     r11, [rsp+78h+var_28]
0x180038b8f  mov     rbx, [r11+30h]
0x180038b93  mov     rbp, [r11+38h]
0x180038b97  mov     rsp, r11
0x180038b9a  pop     r15
0x180038b9c  pop     r14
0x180038b9e  pop     r12
0x180038ba0  pop     rdi
0x180038ba1  pop     rsi
0x180038ba2  retn
```
