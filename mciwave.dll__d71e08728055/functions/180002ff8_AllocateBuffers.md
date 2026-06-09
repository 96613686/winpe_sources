# AllocateBuffers

- ea: `0x180002ff8`
- end: `0x18000310b`
- name: `AllocateBuffers`
- size: `275`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005170`

## callees

- `0x180002ff8`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003036`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003036`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800030e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800030e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800030d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800030d9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800030ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800030ee`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003028`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003028`
- `WINMM!waveOutPrepareHeader` at `0x18000308f`
- `WINMM!waveOutPrepareHeader` at `0x18000308f`
- `WINMM!waveInPrepareHeader` at `0x1800030ab`
- `WINMM!waveInPrepareHeader` at `0x1800030ab`

## pseudocode

```c
__int64 __fastcall AllocateBuffers(__int64 a1)
{
  __int64 i; // rbp
  _DWORD *v3; // rbx
  HGLOBAL v4; // rax
  struct wavehdr_tag *v5; // rdx
  HGLOBAL v6; // rbx

  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 12); i = (unsigned int)(i + 1) )
  {
    if ( *(_DWORD *)(a1 + 148) >= 0xFFFFFFD0 )
      break;
    v3 = 0;
    v4 = GlobalAlloc(2u, (unsigned int)(*(_DWORD *)(a1 + 148) + 48));
    if ( v4 )
      v3 = GlobalLock(v4);
    *(_QWORD *)(a1 + 8 * i + 184) = v3;
    if ( !v3 )
      break;
    v3[6] = 1;
    **(_QWORD **)(a1 + 8 * i + 184) = *(_QWORD *)(a1 + 8 * i + 184) + 48LL;
    *(_DWORD *)(*(_QWORD *)(a1 + 8 * i + 184) + 8LL) = *(_DWORD *)(a1 + 148);
    v5 = *(struct wavehdr_tag **)(a1 + 8 * i + 184);
    if ( *(_DWORD *)(a1 + 28) == 1 )
    {
      if ( waveOutPrepareHeader(*(HWAVEOUT *)(a1 + 48), v5, 0x30u) )
        goto LABEL_13;
      *(_DWORD *)(*(_QWORD *)(a1 + 8 * i + 184) + 24LL) |= 1u;
    }
    else
    {
      if ( waveInPrepareHeader(*(HWAVEIN *)(a1 + 56), v5, 0x30u) )
      {
LABEL_13:
        v6 = GlobalHandle(*(LPCVOID *)(a1 + 8 * i + 184));
        GlobalUnlock(v6);
        GlobalFree(v6);
        *(_QWORD *)(a1 + 8 * i + 184) = 0;
        return (unsigned int)i;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 8 * i + 184) + 12LL) = 0;
    }
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180002ff8  push    rbx
0x180002ffa  push    rbp
0x180002ffb  push    rsi
0x180002ffc  push    rdi
0x180002ffd  sub     rsp, 28h
0x180003001  xor     ebp, ebp
0x180003003  mov     rdi, rcx
0x180003006  cmp     [rcx+0Ch], ebp
0x180003009  jbe     loc_180003100
0x18000300f  mov     eax, [rdi+94h]
0x180003015  add     eax, 30h ; '0'
0x180003018  cmp     eax, 30h ; '0'
0x18000301b  jb      loc_180003100
0x180003021  xor     ebx, ebx
0x180003023  mov     edx, eax; dwBytes
0x180003025  lea     ecx, [rbx+2]; uFlags
0x180003028  call    cs:__imp_GlobalAlloc
0x18000302e  test    rax, rax
0x180003031  jz      short loc_18000303F
0x180003033  mov     rcx, rax; hMem
0x180003036  call    cs:__imp_GlobalLock
0x18000303c  mov     rbx, rax
0x18000303f  mov     [rdi+rbp*8+0B8h], rbx
0x180003047  test    rbx, rbx
0x18000304a  jz      loc_180003100
0x180003050  mov     dword ptr [rbx+18h], 1
0x180003057  mov     r8d, 30h ; '0'; cbwh
0x18000305d  mov     rcx, [rdi+rbp*8+0B8h]
0x180003065  lea     rax, [rcx+30h]
0x180003069  mov     [rcx], rax
0x18000306c  mov     rcx, [rdi+rbp*8+0B8h]
0x180003074  mov     eax, [rdi+94h]
0x18000307a  mov     [rcx+8], eax
0x18000307d  cmp     dword ptr [rdi+1Ch], 1
0x180003081  mov     rdx, [rdi+rbp*8+0B8h]; pwh
0x180003089  jnz     short loc_1800030A7
0x18000308b  mov     rcx, [rdi+30h]; hwo
0x18000308f  call    cs:__imp_waveOutPrepareHeader
0x180003095  test    eax, eax
0x180003097  jnz     short loc_1800030D1
0x180003099  mov     rax, [rdi+rbp*8+0B8h]
0x1800030a1  or      dword ptr [rax+18h], 1
0x1800030a5  jmp     short loc_1800030C4
0x1800030a7  mov     rcx, [rdi+38h]; hwi
0x1800030ab  call    cs:__imp_waveInPrepareHeader
0x1800030b1  test    eax, eax
0x1800030b3  jnz     short loc_1800030D1
0x1800030b5  mov     rax, [rdi+rbp*8+0B8h]
0x1800030bd  mov     dword ptr [rax+0Ch], 0
0x1800030c4  inc     ebp
0x1800030c6  cmp     ebp, [rdi+0Ch]
0x1800030c9  jb      loc_18000300F
0x1800030cf  jmp     short loc_180003100
0x1800030d1  mov     rcx, [rdi+rbp*8+0B8h]; pMem
0x1800030d9  call    cs:__imp_GlobalHandle
0x1800030df  mov     rcx, rax; hMem
0x1800030e2  mov     rbx, rax
0x1800030e5  call    cs:__imp_GlobalUnlock
0x1800030eb  mov     rcx, rbx; hMem
0x1800030ee  call    cs:__imp_GlobalFree
0x1800030f4  mov     qword ptr [rdi+rbp*8+0B8h], 0
0x180003100  mov     eax, ebp
0x180003102  add     rsp, 28h
0x180003106  pop     rdi
0x180003107  pop     rsi
0x180003108  pop     rbp
0x180003109  pop     rbx
0x18000310a  retn
```
