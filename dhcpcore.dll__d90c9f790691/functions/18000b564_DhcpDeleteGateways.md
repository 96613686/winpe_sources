# DhcpDeleteGateways

- ea: `0x18000b564`
- end: `0x18000b63f`
- name: `DhcpDeleteGateways`
- size: `219`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b28c`
- `0x180020c4c`

## callees

- `0x18000b564`
- `0x18000b82c`
- `0x180049534`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b615`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b615`

## pseudocode

```c
__int64 __fastcall DhcpDeleteGateways(__int64 a1)
{
  unsigned int v2; // r14d
  __int64 v3; // rdi
  unsigned int *v4; // rsi
  unsigned int v5; // eax
  unsigned int v6; // ebp
  __int64 result; // rax

  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 34, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, *(_QWORD *)(a1 + 24));
  v2 = *(_DWORD *)(a1 + 492);
  v3 = 0;
  v4 = *(unsigned int **)(a1 + 496);
  if ( v2 )
  {
    do
    {
      v5 = DhcpDeleteIpRoute(a1, 0, 0, v4[v3]);
      v6 = v5;
      if ( v5 && (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_DDJ(1025, 35, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v4[v3], v5, *(_QWORD *)(a1 + 24));
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < v2 );
  }
  else
  {
    v6 = 0;
  }
  if ( v4 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  *(_QWORD *)(a1 + 496) = 0;
  result = v6;
  *(_DWORD *)(a1 + 492) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b564  push    rbx
0x18000b566  push    rbp
0x18000b567  push    rsi
0x18000b568  push    rdi
0x18000b569  push    r14
0x18000b56b  push    r15
0x18000b56d  sub     rsp, 38h
0x18000b571  mov     rbx, rcx
0x18000b574  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000b57b  jz      short loc_18000B597
0x18000b57d  mov     r9, [rbx+18h]
0x18000b581  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b588  mov     edx, 22h ; '"'
0x18000b58d  mov     ecx, 404h
0x18000b592  call    WPP_SF_q
0x18000b597  mov     r14d, [rbx+1ECh]
0x18000b59e  xor     edi, edi
0x18000b5a0  mov     rsi, [rbx+1F0h]
0x18000b5a7  test    r14d, r14d
0x18000b5aa  jz      short loc_18000B5FC
0x18000b5ac  mov     r9d, [rsi+rdi*4]
0x18000b5b0  xor     r8d, r8d
0x18000b5b3  xor     edx, edx
0x18000b5b5  mov     rcx, rbx
0x18000b5b8  call    DhcpDeleteIpRoute
0x18000b5bd  mov     ebp, eax
0x18000b5bf  test    eax, eax
0x18000b5c1  jz      short loc_18000B5F3
0x18000b5c3  test    byte ptr cs:xmmword_1800616A0, 2
0x18000b5ca  jz      short loc_18000B5F3
0x18000b5cc  mov     r8, [rbx+18h]
0x18000b5d0  mov     edx, 23h ; '#'
0x18000b5d5  mov     r9d, [rsi+rdi*4]
0x18000b5d9  mov     ecx, 401h
0x18000b5de  mov     [rsp+68h+var_40], r8
0x18000b5e3  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b5ea  mov     [rsp+68h+var_48], eax
0x18000b5ee  call    WPP_SF_DDJ
0x18000b5f3  inc     edi
0x18000b5f5  cmp     edi, r14d
0x18000b5f8  jb      short loc_18000B5AC
0x18000b5fa  jmp     short loc_18000B5FE
0x18000b5fc  xor     ebp, ebp
0x18000b5fe  test    rsi, rsi
0x18000b601  jz      short loc_18000B61B
0x18000b603  mov     rcx, gs:60h
0x18000b60c  mov     r8, rsi; lpMem
0x18000b60f  xor     edx, edx; dwFlags
0x18000b611  mov     rcx, [rcx+30h]; hHeap
0x18000b615  call    cs:__imp_HeapFree
0x18000b61b  mov     qword ptr [rbx+1F0h], 0
0x18000b626  mov     eax, ebp
0x18000b628  mov     dword ptr [rbx+1ECh], 0
0x18000b632  add     rsp, 38h
0x18000b636  pop     r15
0x18000b638  pop     r14
0x18000b63a  pop     rdi
0x18000b63b  pop     rsi
0x18000b63c  pop     rbp
0x18000b63d  pop     rbx
0x18000b63e  retn
```
