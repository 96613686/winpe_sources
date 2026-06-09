# FlushEventEntryList

- ea: `0x18001bce4`
- end: `0x18001bd8e`
- name: `FlushEventEntryList`
- size: `170`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bd94`

## callees

- `0x18000232a`
- `0x18001bce4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd6c`

## pseudocode

```c
void __fastcall FlushEventEntryList(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)
{
  PCEVENT_DESCRIPTOR Keyword; // rdi
  PEVENT_DATA_DESCRIPTOR *v4; // rbx
  int v5; // edx
  __int64 v6; // rcx
  PEVENT_DATA_DESCRIPTOR v7; // rbx
  HANDLE ProcessHeap; // rax

  if ( EventDescriptor )
  {
    Keyword = EventDescriptor;
    do
    {
      v4 = (PEVENT_DATA_DESCRIPTOR *)&Keyword[1];
      v5 = 2;
      if ( (unsigned int)BYTE5(Keyword[2].Keyword) + 2 > 2 )
      {
        do
        {
          v6 = v5++;
          (*v4)[v6].Reserved1 = 0;
        }
        while ( v5 < BYTE5(Keyword[2].Keyword) + 2 );
      }
      EventWriteTransfer_0(RegHandle, Keyword, 0, 0, BYTE4(Keyword[2].Keyword), *v4);
      Keyword = (PCEVENT_DESCRIPTOR)Keyword[1].Keyword;
      v7 = *v4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
    while ( Keyword );
  }
}

```

## disassembly

```asm
0x18001bce4  test    rdx, rdx
0x18001bce7  jz      locret_18001BD8C
0x18001bced  mov     [rsp+arg_0], rbx
0x18001bcf2  mov     [rsp+arg_8], rsi
0x18001bcf7  push    rdi
0x18001bcf8  sub     rsp, 30h
0x18001bcfc  mov     rdi, rdx
0x18001bcff  mov     rsi, rcx
0x18001bd02  movzx   eax, byte ptr [rdi+2Dh]
0x18001bd06  lea     rbx, [rdi+10h]
0x18001bd0a  mov     edx, 2
0x18001bd0f  add     eax, edx
0x18001bd11  cmp     eax, edx
0x18001bd13  jbe     short loc_18001BD30
0x18001bd15  mov     rax, [rbx]
0x18001bd18  movsxd  rcx, edx
0x18001bd1b  inc     edx
0x18001bd1d  add     rcx, rcx
0x18001bd20  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18001bd25  movzx   eax, byte ptr [rdi+2Dh]
0x18001bd29  add     eax, 2
0x18001bd2c  cmp     edx, eax
0x18001bd2e  jl      short loc_18001BD15
0x18001bd30  movzx   ecx, byte ptr [rdi+2Ch]
0x18001bd34  xor     r9d, r9d; RelatedActivityId
0x18001bd37  mov     rax, [rbx]
0x18001bd3a  xor     r8d, r8d; ActivityId
0x18001bd3d  mov     [rsp+38h+UserData], rax; UserData
0x18001bd42  mov     rdx, rdi; EventDescriptor
0x18001bd45  mov     [rsp+38h+UserDataCount], ecx; UserDataCount
0x18001bd49  mov     rcx, rsi; RegHandle
0x18001bd4c  call    EventWriteTransfer_0
0x18001bd51  mov     rdi, [rdi+18h]
0x18001bd55  mov     rbx, [rbx]
0x18001bd58  call    cs:__imp_GetProcessHeap
0x18001bd5f  nop     dword ptr [rax+rax+00h]
0x18001bd64  mov     r8, rbx; lpMem
0x18001bd67  xor     edx, edx; dwFlags
0x18001bd69  mov     rcx, rax; hHeap
0x18001bd6c  call    cs:__imp_HeapFree
0x18001bd73  nop     dword ptr [rax+rax+00h]
0x18001bd78  test    rdi, rdi
0x18001bd7b  jnz     short loc_18001BD02
0x18001bd7d  mov     rbx, [rsp+38h+arg_0]
0x18001bd82  mov     rsi, [rsp+38h+arg_8]
0x18001bd87  add     rsp, 30h
0x18001bd8b  pop     rdi
0x18001bd8c  retn
```
