# SocketBrokerTable::Find(_GUID *,ushort const *,SocketBrokerContext * *)

- ea: `0x180003b60`
- end: `0x180003c73`
- name: `?Find@SocketBrokerTable@@QEAAKPEAU_GUID@@PEBGPEAPEAVSocketBrokerContext@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _GUID *, const unsigned __int16 *, struct SocketBrokerContext **)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004a30`
- `0x1800261d8`
- `0x18002688c`

## callees

- `0x180003b60`
- `0x180003c7c`
- `0x180003d00`
- `0x18000a0a0`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180003bdf`
- `ntdll!RtlLookupEntryHashTable` at `0x180003bdf`
- `ntdll!RtlGetNextEntryHashTable` at `0x180003c4c`
- `ntdll!RtlGetNextEntryHashTable` at `0x180003c4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003bc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003bc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c23`

## string_xrefs

- `0x180003c65`: `SocketBrokerTable: Failed to get Hash index`

## pseudocode

```c
__int64 __fastcall SocketBrokerTable::Find(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        struct SocketBrokerContext **a4)
{
  SocketBrokerTable *v7; // rcx
  unsigned int Hash; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  char v12; // di
  __int64 i; // rax
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  int v17; // r9d
  int v18; // r8d
  __int128 v20; // [rsp+20h] [rbp-58h] BYREF
  __int64 v21; // [rsp+30h] [rbp-48h]
  unsigned int v22; // [rsp+88h] [rbp+10h] BYREF
  int v23; // [rsp+8Ch] [rbp+14h]

  v23 = HIDWORD(a2);
  v22 = 0;
  v21 = 0;
  *a4 = 0;
  v20 = 0;
  SocketBrokerTable::Initialize(lpCriticalSection);
  Hash = SocketBrokerTable::GetHash(v7, a3, &v22);
  v11 = Hash;
  if ( Hash )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, v9, L"SocketBrokerTable: Failed to get Hash index", Hash);
  }
  else
  {
    v20 = 0;
    v12 = 0;
    EnterCriticalSection(lpCriticalSection);
    if ( LOBYTE(lpCriticalSection[2].DebugInfo) )
    {
      for ( i = RtlLookupEntryHashTable(&lpCriticalSection[1], v22, &v20);
            i;
            i = RtlGetNextEntryHashTable(&lpCriticalSection[1], &v20) )
      {
        v14 = *(_QWORD *)(i + 48);
        if ( v14 )
        {
          v15 = a3;
          v16 = v14 - (_QWORD)a3;
          do
          {
            v17 = *(const unsigned __int16 *)((char *)v15 + v16);
            v18 = *v15 - v17;
            if ( v18 )
              break;
            ++v15;
          }
          while ( v17 );
          if ( !v18 )
          {
            v12 = 1;
            _InterlockedAdd((volatile signed __int32 *)(i + 24), 1u);
            *a4 = (struct SocketBrokerContext *)i;
            break;
          }
        }
      }
    }
    LeaveCriticalSection(lpCriticalSection);
    if ( !v12 )
      return 1168;
  }
  return v11;
}

```

## disassembly

```asm
0x180003b60  mov     rax, rsp
0x180003b63  mov     [rax+10h], rdx
0x180003b67  push    rbx
0x180003b68  push    rbp
0x180003b69  push    rsi
0x180003b6a  push    rdi
0x180003b6b  push    r14
0x180003b6d  push    r15
0x180003b6f  sub     rsp, 48h
0x180003b73  mov     dword ptr [rax+10h], 0
0x180003b7a  xorps   xmm0, xmm0
0x180003b7d  xor     eax, eax
0x180003b7f  mov     r14, r9
0x180003b82  mov     [rsp+78h+var_48], rax
0x180003b87  mov     r15, r8
0x180003b8a  mov     [r9], rax
0x180003b8d  mov     rsi, rcx
0x180003b90  movups  [rsp+78h+var_58], xmm0
0x180003b95  call    ?Initialize@SocketBrokerTable@@QEAAKXZ; SocketBrokerTable::Initialize(void)
0x180003b9a  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x180003ba2  mov     rdx, r15; unsigned __int16 *
0x180003ba5  call    ?GetHash@SocketBrokerTable@@AEAAKPEBGPEAK@Z; SocketBrokerTable::GetHash(ushort const *,ulong *)
0x180003baa  mov     ebx, eax
0x180003bac  test    eax, eax
0x180003bae  jnz     loc_180003C54
0x180003bb4  xorps   xmm0, xmm0
0x180003bb7  mov     rcx, rsi; lpCriticalSection
0x180003bba  movdqu  [rsp+78h+var_58], xmm0
0x180003bc0  xor     dil, dil
0x180003bc3  call    cs:__imp_EnterCriticalSection
0x180003bc9  cmp     [rsi+50h], dil
0x180003bcd  jz      short loc_180003C20
0x180003bcf  mov     edx, [rsp+78h+arg_8]
0x180003bd6  lea     r8, [rsp+78h+var_58]
0x180003bdb  lea     rcx, [rsi+28h]
0x180003bdf  call    cs:__imp_RtlLookupEntryHashTable
0x180003be5  test    rax, rax
0x180003be8  jz      short loc_180003C20
0x180003bea  mov     rdx, [rax+30h]
0x180003bee  test    rdx, rdx
0x180003bf1  jz      short loc_180003C43
0x180003bf3  mov     rcx, r15
0x180003bf6  sub     rdx, r15
0x180003bf9  movzx   r8d, word ptr [rcx]
0x180003bfd  movzx   r9d, word ptr [rcx+rdx]
0x180003c02  sub     r8d, r9d
0x180003c05  jnz     short loc_180003C10
0x180003c07  add     rcx, 2
0x180003c0b  test    r9d, r9d
0x180003c0e  jnz     short loc_180003BF9
0x180003c10  test    r8d, r8d
0x180003c13  jnz     short loc_180003C43
0x180003c15  lea     edi, [r8+1]
0x180003c19  lock add [rax+18h], edi
0x180003c1d  mov     [r14], rax
0x180003c20  mov     rcx, rsi; lpCriticalSection
0x180003c23  call    cs:__imp_LeaveCriticalSection
0x180003c29  test    dil, dil
0x180003c2c  mov     eax, 490h
0x180003c31  cmovz   ebx, eax
0x180003c34  mov     eax, ebx
0x180003c36  add     rsp, 48h
0x180003c3a  pop     r15
0x180003c3c  pop     r14
0x180003c3e  pop     rdi
0x180003c3f  pop     rsi
0x180003c40  pop     rbp
0x180003c41  pop     rbx
0x180003c42  retn
0x180003c43  lea     rdx, [rsp+78h+var_58]
0x180003c48  lea     rcx, [rsi+28h]
0x180003c4c  call    cs:__imp_RtlGetNextEntryHashTable
0x180003c52  jmp     short loc_180003BE5
0x180003c54  mov     edi, 1
0x180003c59  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, dil
0x180003c60  jz      short loc_180003C34
0x180003c62  mov     r9d, ebx
0x180003c65  lea     r8, aSocketbrokerta_0; "SocketBrokerTable: Failed to get Hash i"...
0x180003c6c  call    McTemplateU0zq_EventWriteTransfer
0x180003c71  jmp     short loc_180003C34
```
