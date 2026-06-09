# CopyAndAllocateMatchValue(tagHELPER_ATTRIBUTE *,StoredMatchValue const *)

- ea: `0x18000d134`
- end: `0x18000d238`
- name: `?CopyAndAllocateMatchValue@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBUStoredMatchValue@@@Z`
- size: `260`
- prototype: `int(struct tagHELPER_ATTRIBUTE *, const struct StoredMatchValue *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bca0`

## callees

- `0x18000c598`
- `0x18000d134`
- `0x180010684`
- `0x180013686`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d1a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyAndAllocateMatchValue(
        struct tagHELPER_ATTRIBUTE *a1,
        const struct StoredMatchValue *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v5; // r9
  int v6; // edi
  const unsigned __int16 *v7; // r8
  SIZE_T v8; // rbp
  BYTE *v9; // rax
  BYTE *v10; // r14
  SIZE_T i; // rcx
  unsigned __int16 *v12; // r9

  if ( *((_QWORD *)a2 + 3) < 8u )
    v5 = (unsigned __int16 *)a2;
  else
    v5 = *(unsigned __int16 **)a2;
  v6 = UtilAssembleStringsWithAlloc(&a1->pwszName, 0xFFFFu, a3, v5);
  if ( v6 >= 0 )
  {
    a1->type = *((_DWORD *)a2 + 8);
    switch ( *((_DWORD *)a2 + 8) )
    {
      case 7:
        a1->Boolean = *((_DWORD *)a2 + 24);
        break;
      case 0xA:
        v12 = (unsigned __int16 *)((char *)a2 + 64);
        if ( *((_QWORD *)a2 + 11) >= 8u )
          v12 = *(unsigned __int16 **)v12;
        v6 = UtilAssembleStringsWithAlloc(&a1->PWStr, 0xFFFFu, v7, v12);
        break;
      case 0xE:
        v8 = *((_QWORD *)a2 + 6) - *((_QWORD *)a2 + 5);
        v9 = (BYTE *)CoTaskMemAlloc(v8);
        v10 = v9;
        if ( v9 )
        {
          memset_0(v9, 0, v8);
          for ( i = 0; i < v8; ++i )
            v10[i] = *(_BYTE *)(i + *((_QWORD *)a2 + 5));
          a1->OctetString.lpValue = v10;
          a1->Boolean = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v8);
        }
        else
        {
          v6 = -2147024882;
        }
        break;
      default:
        v6 = -2147467263;
        break;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d134  mov     [rsp+arg_8], rbx
0x18000d139  mov     [rsp+arg_10], rbp
0x18000d13e  push    rsi
0x18000d13f  push    rdi
0x18000d140  push    r14
0x18000d142  sub     rsp, 30h
0x18000d146  mov     rbx, rdx
0x18000d149  mov     rsi, rcx
0x18000d14c  cmp     qword ptr [rdx+18h], 8
0x18000d151  jb      short loc_18000D158
0x18000d153  mov     r9, [rdx]
0x18000d156  jmp     short loc_18000D15B
0x18000d158  mov     r9, rbx; unsigned __int16 *
0x18000d15b  mov     ebp, 0FFFFh
0x18000d160  mov     edx, ebp; unsigned int
0x18000d162  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000d167  mov     edi, eax
0x18000d169  test    eax, eax
0x18000d16b  js      loc_18000D222
0x18000d171  mov     ecx, [rbx+20h]
0x18000d174  mov     [rsi+8], ecx
0x18000d177  cmp     dword ptr [rbx+20h], 7
0x18000d17b  jz      loc_18000D21C
0x18000d181  cmp     dword ptr [rbx+20h], 0Ah
0x18000d185  jz      short loc_18000D1FF
0x18000d187  cmp     dword ptr [rbx+20h], 0Eh
0x18000d18b  jz      short loc_18000D197
0x18000d18d  mov     edi, 80004001h
0x18000d192  jmp     loc_18000D222
0x18000d197  mov     rbp, [rbx+30h]
0x18000d19b  sub     rbp, [rbx+28h]
0x18000d19f  mov     rcx, rbp; cb
0x18000d1a2  call    cs:__imp_CoTaskMemAlloc
0x18000d1a9  nop     dword ptr [rax+rax+00h]
0x18000d1ae  mov     r14, rax
0x18000d1b1  test    rax, rax
0x18000d1b4  jnz     short loc_18000D1BD
0x18000d1b6  mov     edi, 8007000Eh
0x18000d1bb  jmp     short loc_18000D222
0x18000d1bd  mov     r8, rbp; Size
0x18000d1c0  xor     edx, edx; Val
0x18000d1c2  mov     rcx, r14; void *
0x18000d1c5  call    memset_0
0x18000d1ca  nop
0x18000d1cb  xor     ecx, ecx
0x18000d1cd  test    rbp, rbp
0x18000d1d0  jz      short loc_18000D1E5
0x18000d1d2  mov     rax, [rbx+28h]
0x18000d1d6  mov     dl, [rcx+rax]
0x18000d1d9  mov     [r14+rcx], dl
0x18000d1dd  inc     rcx
0x18000d1e0  cmp     rcx, rbp
0x18000d1e3  jb      short loc_18000D1D2
0x18000d1e5  mov     [rsp+48h+arg_0], 0
0x18000d1ee  mov     [rsi+18h], r14
0x18000d1f2  mov     rcx, rbp
0x18000d1f5  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000d1fa  mov     [rsi+10h], eax
0x18000d1fd  jmp     short loc_18000D222
0x18000d1ff  lea     r9, [rbx+40h]
0x18000d203  cmp     qword ptr [r9+18h], 8
0x18000d208  jb      short loc_18000D20D
0x18000d20a  mov     r9, [r9]; unsigned __int16 *
0x18000d20d  lea     rcx, [rsi+10h]; unsigned __int16 **
0x18000d211  mov     edx, ebp; unsigned int
0x18000d213  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000d218  mov     edi, eax
0x18000d21a  jmp     short loc_18000D222
0x18000d21c  mov     eax, [rbx+60h]
0x18000d21f  mov     [rsi+10h], eax
0x18000d222  mov     eax, edi
0x18000d224  mov     rbx, [rsp+48h+arg_8]
0x18000d229  mov     rbp, [rsp+48h+arg_10]
0x18000d22e  add     rsp, 30h
0x18000d232  pop     r14
0x18000d234  pop     rdi
0x18000d235  pop     rsi
0x18000d236  retn
```
