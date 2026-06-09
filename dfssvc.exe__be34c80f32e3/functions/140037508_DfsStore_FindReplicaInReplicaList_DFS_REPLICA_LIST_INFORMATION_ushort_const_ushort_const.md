# DfsStore::FindReplicaInReplicaList(_DFS_REPLICA_LIST_INFORMATION_ *,ushort const *,ushort const *)

- ea: `0x140037508`
- end: `0x14003764c`
- name: `?FindReplicaInReplicaList@DfsStore@@QEAAKPEAU_DFS_REPLICA_LIST_INFORMATION_@@PEBG1@Z`
- size: `324`
- prototype: `unsigned int __fastcall(DfsStore *__hidden this, struct _DFS_REPLICA_LIST_INFORMATION_ *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400364d4`
- `0x140039ae4`
- `0x14003a258`
- `0x14003a3d0`

## callees

- `0x140037508`
- `0x14004a454`
- `0x1400586a8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1400375a8`
- `ntdll!RtlCompareUnicodeString` at `0x1400375c7`
- `ntdll!RtlCompareUnicodeString` at `0x140037613`
- `ntdll!RtlCompareUnicodeString` at `0x1400375a8`
- `ntdll!RtlCompareUnicodeString` at `0x1400375c7`
- `ntdll!RtlCompareUnicodeString` at `0x140037613`

## pseudocode

```c
__int64 __fastcall DfsStore::FindReplicaInReplicaList(
        DfsStore *this,
        struct _DFS_REPLICA_LIST_INFORMATION_ *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int i; // ebx
  __int64 LocalMachineName; // rax
  const UNICODE_STRING *v8; // rdi
  const UNICODE_STRING *v9; // rbp
  PWSTR Buffer; // rax
  UNICODE_STRING v12; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-18h] BYREF

  String1 = 0;
  i = -1;
  v12 = 0;
  String2 = 0;
  if ( !(unsigned int)DfsRtlInitUnicodeStringEx(&v12, a3) && !(unsigned int)DfsRtlInitUnicodeStringEx(&String2, a4) )
  {
    LocalMachineName = DfsGetLocalMachineName(3);
    if ( !(unsigned int)DfsRtlInitUnicodeStringEx(&String1, LocalMachineName) )
    {
      for ( i = 0; i < *((_DWORD *)a2 + 3); ++i )
      {
        v8 = (const UNICODE_STRING *)(*((_QWORD *)a2 + 2) + ((unsigned __int64)i << 6));
        if ( !RtlCompareUnicodeString(v8 + 3, &String2, 1u) )
        {
          v9 = v8 + 2;
          if ( !RtlCompareUnicodeString(v8 + 2, &v12, 1u) )
            return i;
          if ( !i )
          {
            if ( v9->Length == 2 )
            {
              if ( *v8[2].Buffer == 46 )
                goto LABEL_14;
            }
            else if ( v9->Length == 4 )
            {
              Buffer = v8[2].Buffer;
              if ( *Buffer == 46 && !Buffer[1] )
              {
LABEL_14:
                if ( !RtlCompareUnicodeString(&String1, &v12, 1u) )
                  return i;
              }
            }
          }
        }
      }
    }
  }
  return i;
}

```

## disassembly

```asm
0x140037508  mov     rax, rsp
0x14003750b  mov     [rax+8], rbx
0x14003750f  mov     [rax+10h], rbp
0x140037513  mov     [rax+18h], rsi
0x140037517  mov     [rax+20h], rdi
0x14003751b  push    r14
0x14003751d  sub     rsp, 50h
0x140037521  xorps   xmm0, xmm0
0x140037524  lea     rcx, [rax-38h]
0x140037528  mov     rsi, rdx
0x14003752b  xorps   xmm1, xmm1
0x14003752e  mov     rdx, r8
0x140037531  mov     rdi, r9
0x140037534  movups  xmmword ptr [rax-18h], xmm0
0x140037538  or      ebx, 0FFFFFFFFh
0x14003753b  movups  xmmword ptr [rax-38h], xmm1
0x14003753f  movups  xmmword ptr [rax-28h], xmm0
0x140037543  call    DfsRtlInitUnicodeStringEx
0x140037548  xor     r14d, r14d
0x14003754b  test    eax, eax
0x14003754d  jnz     loc_14003762E
0x140037553  mov     rdx, rdi
0x140037556  lea     rcx, [rsp+58h+String2]
0x14003755b  call    DfsRtlInitUnicodeStringEx
0x140037560  test    eax, eax
0x140037562  jnz     loc_14003762E
0x140037568  lea     ecx, [rax+3]
0x14003756b  call    ?DfsGetLocalMachineName@@YAPEBGW4DFS_HOST_NAME_TYPE@CLocalMachine@@@Z; DfsGetLocalMachineName(CLocalMachine::DFS_HOST_NAME_TYPE)
0x140037570  mov     rdx, rax
0x140037573  lea     rcx, [rsp+58h+String1]
0x140037578  call    DfsRtlInitUnicodeStringEx
0x14003757d  test    eax, eax
0x14003757f  jnz     loc_14003762E
0x140037585  mov     ebx, r14d
0x140037588  cmp     [rsi+0Ch], r14d
0x14003758c  jbe     loc_14003762E
0x140037592  mov     edi, ebx
0x140037594  lea     rdx, [rsp+58h+String2]; String2
0x140037599  shl     rdi, 6
0x14003759d  mov     r8b, 1; CaseInsensitive
0x1400375a0  add     rdi, [rsi+10h]
0x1400375a4  lea     rcx, [rdi+30h]; String1
0x1400375a8  call    cs:__imp_RtlCompareUnicodeString
0x1400375af  nop     dword ptr [rax+rax+00h]
0x1400375b4  test    eax, eax
0x1400375b6  jnz     short loc_140037623
0x1400375b8  lea     rbp, [rdi+20h]
0x1400375bc  mov     r8b, 1; CaseInsensitive
0x1400375bf  mov     rcx, rbp; String1
0x1400375c2  lea     rdx, [rsp+58h+var_38]; String2
0x1400375c7  call    cs:__imp_RtlCompareUnicodeString
0x1400375ce  nop     dword ptr [rax+rax+00h]
0x1400375d3  test    eax, eax
0x1400375d5  jz      short loc_14003762E
0x1400375d7  test    ebx, ebx
0x1400375d9  jnz     short loc_140037623
0x1400375db  cmp     word ptr [rbp+0], 2
0x1400375e0  jnz     short loc_1400375EE
0x1400375e2  mov     rax, [rdi+28h]
0x1400375e6  cmp     word ptr [rax], 2Eh ; '.'
0x1400375ea  jz      short loc_140037606
0x1400375ec  jmp     short loc_140037623
0x1400375ee  cmp     word ptr [rbp+0], 4
0x1400375f3  jnz     short loc_140037623
0x1400375f5  mov     rax, [rdi+28h]
0x1400375f9  cmp     word ptr [rax], 2Eh ; '.'
0x1400375fd  jnz     short loc_140037623
0x1400375ff  cmp     [rax+2], r14w
0x140037604  jnz     short loc_140037623
0x140037606  mov     r8b, 1; CaseInsensitive
0x140037609  lea     rdx, [rsp+58h+var_38]; String2
0x14003760e  lea     rcx, [rsp+58h+String1]; String1
0x140037613  call    cs:__imp_RtlCompareUnicodeString
0x14003761a  nop     dword ptr [rax+rax+00h]
0x14003761f  test    eax, eax
0x140037621  jz      short loc_14003762E
0x140037623  inc     ebx
0x140037625  cmp     ebx, [rsi+0Ch]
0x140037628  jb      loc_140037592
0x14003762e  mov     rbp, [rsp+58h+arg_8]
0x140037633  mov     eax, ebx
0x140037635  mov     rbx, [rsp+58h+arg_0]
0x14003763a  mov     rsi, [rsp+58h+arg_10]
0x14003763f  mov     rdi, [rsp+58h+arg_18]
0x140037644  add     rsp, 50h
0x140037648  pop     r14
0x14003764a  retn
```
