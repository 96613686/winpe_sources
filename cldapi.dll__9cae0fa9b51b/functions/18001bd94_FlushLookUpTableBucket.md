# FlushLookUpTableBucket

- ea: `0x18001bd94`
- end: `0x18001be53`
- name: `FlushLookUpTableBucket`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c1fc`
- `0x18001c5e0`

## callees

- `0x18001bce4`
- `0x18001bd94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bdba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bdba`

## pseudocode

```c
__int64 __fastcall FlushLookUpTableBucket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  RTL_SRWLOCK *v5; // rbp
  const EVENT_DESCRIPTOR *v6; // rsi
  unsigned int v7; // edi
  const EVENT_DESCRIPTOR **p_Keyword; // rax
  const EVENT_DESCRIPTOR *v9; // rcx
  const EVENT_DESCRIPTOR *v10; // r8
  const EVENT_DESCRIPTOR *v11; // rdx
  const EVENT_DESCRIPTOR **v12; // rcx
  const EVENT_DESCRIPTOR *v13; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8LL * a2) )
    return 0;
  v5 = (RTL_SRWLOCK *)(a1 + 264);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
  v6 = *(const EVENT_DESCRIPTOR **)(a1 + 8 * v2);
  *(_QWORD *)(a1 + 8 * v2) = 0;
  v7 = 0;
  v13 = v6;
  if ( v6 )
  {
    p_Keyword = &v13;
    v9 = v6;
    do
    {
      v10 = *(const EVENT_DESCRIPTOR **)&v9[2].Id;
      *(_QWORD *)&v9[2].Id = 0;
      p_Keyword = (const EVENT_DESCRIPTOR **)&(*p_Keyword)[1].Keyword;
      v11 = *p_Keyword;
      if ( *p_Keyword )
      {
        do
        {
          v12 = (const EVENT_DESCRIPTOR **)&v11[2];
          v11 = *(const EVENT_DESCRIPTOR **)&v11[2].Id;
        }
        while ( v11 );
      }
      else
      {
        v12 = p_Keyword;
      }
      *v12 = v10;
      ++v7;
      v9 = *p_Keyword;
    }
    while ( *p_Keyword );
  }
  *(_DWORD *)(a1 + 256) -= v7;
  ReleaseSRWLockExclusive(v5);
  FlushEventEntryList(*(_QWORD *)(*(_QWORD *)(a1 + 328) + 32LL), v6);
  return v7;
}

```

## disassembly

```asm
0x18001bd94  push    rbx
0x18001bd96  push    rbp
0x18001bd97  push    rsi
0x18001bd98  push    rdi
0x18001bd99  sub     rsp, 28h
0x18001bd9d  mov     edi, edx
0x18001bd9f  mov     rbx, rcx
0x18001bda2  cmp     qword ptr [rcx+rdi*8], 0
0x18001bda7  jnz     short loc_18001BDB0
0x18001bda9  xor     eax, eax
0x18001bdab  jmp     loc_18001BE49
0x18001bdb0  lea     rbp, [rcx+108h]
0x18001bdb7  mov     rcx, rbp; SRWLock
0x18001bdba  call    cs:__imp_AcquireSRWLockExclusive
0x18001bdc1  nop     dword ptr [rax+rax+00h]
0x18001bdc6  mov     rsi, [rbx+rdi*8]
0x18001bdca  mov     qword ptr [rbx+rdi*8], 0
0x18001bdd2  xor     edi, edi
0x18001bdd4  mov     [rsp+48h+arg_0], rsi
0x18001bdd9  test    rsi, rsi
0x18001bddc  jz      short loc_18001BE1F
0x18001bdde  lea     rax, [rsp+48h+arg_0]
0x18001bde3  mov     rcx, rsi
0x18001bde6  mov     r8, [rcx+20h]
0x18001bdea  mov     qword ptr [rcx+20h], 0
0x18001bdf2  mov     rax, [rax]
0x18001bdf5  add     rax, 18h
0x18001bdf9  mov     rdx, [rax]
0x18001bdfc  test    rdx, rdx
0x18001bdff  jz      short loc_18001BE0F
0x18001be01  lea     rcx, [rdx+20h]
0x18001be05  mov     rdx, [rcx]
0x18001be08  test    rdx, rdx
0x18001be0b  jnz     short loc_18001BE01
0x18001be0d  jmp     short loc_18001BE12
0x18001be0f  mov     rcx, rax
0x18001be12  mov     [rcx], r8
0x18001be15  inc     edi
0x18001be17  mov     rcx, [rax]
0x18001be1a  test    rcx, rcx
0x18001be1d  jnz     short loc_18001BDE6
0x18001be1f  sub     [rbx+100h], edi
0x18001be25  mov     rcx, rbp; SRWLock
0x18001be28  call    cs:__imp_ReleaseSRWLockExclusive
0x18001be2f  nop     dword ptr [rax+rax+00h]
0x18001be34  mov     rcx, [rbx+148h]
0x18001be3b  mov     rdx, rsi; EventDescriptor
0x18001be3e  mov     rcx, [rcx+20h]; RegHandle
0x18001be42  call    FlushEventEntryList
0x18001be47  mov     eax, edi
0x18001be49  add     rsp, 28h
0x18001be4d  pop     rdi
0x18001be4e  pop     rsi
0x18001be4f  pop     rbp
0x18001be50  pop     rbx
0x18001be51  retn
```
