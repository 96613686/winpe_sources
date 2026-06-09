# CNetDiagClient::RepairWithoutUI(tagRepairInfoEx *,ulong,int,NDFRepairState)

- ea: `0x18001a6b4`
- end: `0x18001a7ce`
- name: `?RepairWithoutUI@CNetDiagClient@@QEAAJPEAUtagRepairInfoEx@@KHW4NDFRepairState@@@Z`
- size: `282`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014c90`
- `0x180014d40`
- `0x180015710`
- `0x18001b6e0`
- `0x18001b7a0`

## callees

- `0x18000ec70`
- `0x18000f8b8`
- `0x18001a6b4`
- `0x18001cc3c`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18001a777`
- `KERNEL32!GetTickCount` at `0x18001a7a4`
- `KERNEL32!GetTickCount` at `0x18001a777`
- `KERNEL32!GetTickCount` at `0x18001a7a4`

## pseudocode

```c
int __fastcall CNetDiagClient::RepairWithoutUI(CNetDiagClient *a1, __int64 a2, DWORD a3, int a4, int a5)
{
  int result; // eax
  unsigned int v9; // r9d
  unsigned int v10; // ecx
  __int64 v11; // r8
  DWORD TickCount; // esi
  DWORD v13; // edx
  DWORD v14; // eax

  if ( !a2 )
    return -2147024809;
  v9 = *((_DWORD *)a1 + 492);
  *((_DWORD *)a1 + 493) = -1;
  if ( v9 )
  {
    v10 = 0;
    while ( 1 )
    {
      v11 = 152LL * v10;
      if ( *(_DWORD *)(a2 + 104) == *(_DWORD *)((char *)a1 + v11 + 272)
        && *(_QWORD *)a2 == *(_QWORD *)((char *)a1 + v11 + 168)
        && *(_QWORD *)(a2 + 8) == _mm_srli_si128(*(__m128i *)((char *)a1 + v11 + 168), 8).m128i_u64[0] )
      {
        break;
      }
      if ( ++v10 >= v9 )
        goto LABEL_11;
    }
    *((_DWORD *)a1 + 493) = v10;
  }
LABEL_11:
  if ( *((_DWORD *)a1 + 493) == -1 )
  {
    if ( *(_QWORD *)a2 == 0x4155A635A009E5ECLL && *(_QWORD *)(a2 + 8) == 0xE5C117403D4808BBuLL && !a5 )
      return CPushButtonReset::Execute();
    else
      return -2147024894;
  }
  else
  {
    TickCount = GetTickCount();
    result = CNetDiagClient::Repair((__int64)a1, *((_DWORD *)a1 + 493), a3, a5);
    if ( result >= 0 && a4 )
    {
      v13 = -1;
      if ( a3 == -1 )
        return CNetDiagClient::Validate(a1, v13);
      v14 = GetTickCount();
      v13 = TickCount + a3 - v14;
      if ( TickCount + a3 != v14 )
        return CNetDiagClient::Validate(a1, v13);
      else
        return -2147024638;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a6b4  push    rbp
0x18001a6b6  push    rbx
0x18001a6b7  push    rsi
0x18001a6b8  push    rdi
0x18001a6b9  push    r14
0x18001a6bb  lea     rbp, [rsp-2Fh]
0x18001a6c0  sub     rsp, 90h
0x18001a6c7  mov     r14d, r9d
0x18001a6ca  mov     edi, r8d
0x18001a6cd  mov     rbx, rcx
0x18001a6d0  test    rdx, rdx
0x18001a6d3  jnz     short loc_18001A6DF
0x18001a6d5  mov     eax, 80070057h
0x18001a6da  jmp     loc_18001A7C0
0x18001a6df  mov     r9d, [rcx+7B0h]
0x18001a6e6  mov     dword ptr [rcx+7B4h], 0FFFFFFFFh
0x18001a6f0  test    r9d, r9d
0x18001a6f3  jz      short loc_18001A73F
0x18001a6f5  xor     ecx, ecx
0x18001a6f7  mov     eax, ecx
0x18001a6f9  imul    r8, rax, 98h
0x18001a700  mov     eax, [r8+rbx+110h]
0x18001a708  cmp     [rdx+68h], eax
0x18001a70b  jnz     short loc_18001A730
0x18001a70d  movups  xmm2, xmmword ptr [r8+rbx+0A8h]
0x18001a716  movq    rax, xmm2
0x18001a71b  cmp     [rdx], rax
0x18001a71e  jnz     short loc_18001A730
0x18001a720  psrldq  xmm2, 8
0x18001a725  movq    rax, xmm2
0x18001a72a  cmp     [rdx+8], rax
0x18001a72e  jz      short loc_18001A739
0x18001a730  inc     ecx
0x18001a732  cmp     ecx, r9d
0x18001a735  jb      short loc_18001A6F7
0x18001a737  jmp     short loc_18001A73F
0x18001a739  mov     [rbx+7B4h], ecx
0x18001a73f  mov     eax, [rbx+7B4h]
0x18001a745  cmp     eax, 0FFFFFFFFh
0x18001a748  jnz     short loc_18001A777
0x18001a74a  mov     rax, [rdx]
0x18001a74d  cmp     rax, qword ptr cs:xmmword_180027A30
0x18001a754  jnz     short loc_18001A770
0x18001a756  mov     rax, [rdx+8]
0x18001a75a  cmp     rax, qword ptr cs:xmmword_180027A30+8
0x18001a761  jnz     short loc_18001A770
0x18001a763  cmp     [rbp+4Fh+arg_20], 0
0x18001a767  jnz     short loc_18001A770
0x18001a769  call    ?Execute@CPushButtonReset@@SAJXZ; CPushButtonReset::Execute(void)
0x18001a76e  jmp     short loc_18001A7C0
0x18001a770  mov     eax, 80070002h
0x18001a775  jmp     short loc_18001A7C0
0x18001a777  call    cs:__imp_GetTickCount
0x18001a77d  mov     r9d, [rbp+4Fh+arg_20]
0x18001a781  mov     r8d, edi
0x18001a784  mov     edx, [rbx+7B4h]
0x18001a78a  mov     rcx, rbx
0x18001a78d  mov     esi, eax
0x18001a78f  call    ?Repair@CNetDiagClient@@IEAAJKKW4NDFRepairState@@@Z; CNetDiagClient::Repair(ulong,ulong,NDFRepairState)
0x18001a794  test    eax, eax
0x18001a796  js      short loc_18001A7C0
0x18001a798  test    r14d, r14d
0x18001a79b  jz      short loc_18001A7C0
0x18001a79d  or      edx, 0FFFFFFFFh; unsigned int
0x18001a7a0  cmp     edi, edx
0x18001a7a2  jz      short loc_18001A7B8
0x18001a7a4  call    cs:__imp_GetTickCount
0x18001a7aa  lea     edx, [rsi+rdi]
0x18001a7ad  sub     edx, eax
0x18001a7af  jnz     short loc_18001A7B8
0x18001a7b1  mov     eax, 80070102h
0x18001a7b6  jmp     short loc_18001A7C0
0x18001a7b8  mov     rcx, rbx; this
0x18001a7bb  call    ?Validate@CNetDiagClient@@QEAAJK@Z; CNetDiagClient::Validate(ulong)
0x18001a7c0  add     rsp, 90h
0x18001a7c7  pop     r14
0x18001a7c9  pop     rdi
0x18001a7ca  pop     rsi
0x18001a7cb  pop     rbx
0x18001a7cc  pop     rbp
0x18001a7cd  retn
```
