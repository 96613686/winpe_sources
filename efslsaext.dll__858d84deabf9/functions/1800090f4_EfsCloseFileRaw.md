# EfsCloseFileRaw

- ea: `0x1800090f4`
- end: `0x1800091f8`
- name: `EfsCloseFileRaw`
- size: `260`
- prototype: `void __fastcall(_QWORD *lpMem)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007430`
- `0x180007e60`

## callees

- `0x1800064f4`
- `0x18000829c`
- `0x1800090f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091d1`
- `EFSCORE!EfsDllOefsReleaseExclusiveOperation` at `0x180009139`
- `EFSCORE!EfsDllOefsReleaseExclusiveOperation` at `0x180009164`
- `EFSCORE!EfsDllOefsReleaseExclusiveOperation` at `0x180009139`
- `EFSCORE!EfsDllOefsReleaseExclusiveOperation` at `0x180009164`

## pseudocode

```c
void __fastcall EfsCloseFileRaw(_QWORD *lpMem)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ecx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // ecx
  HANDLE ProcessHeap; // rax
  __int128 v9; // [rsp+30h] [rbp-28h] BYREF
  __int128 v10; // [rsp+40h] [rbp-18h]

  if ( lpMem )
  {
    v9 = 0;
    v10 = 0;
    if ( *(_DWORD *)lpMem == 1 )
    {
      if ( (*((_BYTE *)lpMem + 4) & 2) == 0 )
      {
        v2 = lpMem[1];
        if ( (*((_BYTE *)lpMem + 4) & 1) != 0 )
        {
          v3 = EfsDllOefsReleaseExclusiveOperation(v2, 0, 0);
          if ( v3 < 0 )
            fnEfsLogTrace1(v4, (unsigned int)EFS_API_ERROR, v3, 11, 69);
          v5 = 0;
        }
        else
        {
          v6 = EfsDllOefsReleaseExclusiveOperation(v2, 0, 0);
          if ( v6 < 0 )
            fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, v6, 11, 96);
          *((_QWORD *)&v10 + 1) = lpMem[3];
          *((_QWORD *)&v9 + 1) = lpMem[4];
          LODWORD(v9) = *((_DWORD *)lpMem + 4);
          *(_QWORD *)&v10 = 0;
          v5 = lpMem[5];
        }
        CleanupOpenFileStreams(&v9, v5, lpMem[1]);
        *((_DWORD *)lpMem + 1) |= 2u;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x1800090f4  test    rcx, rcx
0x1800090f7  jz      locret_1800091F7
0x1800090fd  mov     [rsp+arg_0], rcx
0x180009102  push    rbx
0x180009103  sub     rsp, 50h
0x180009107  mov     rbx, rcx
0x18000910a  xorps   xmm0, xmm0
0x18000910d  movups  [rsp+58h+var_28], xmm0
0x180009112  movups  [rsp+58h+var_18], xmm0
0x180009117  cmp     dword ptr [rcx], 1
0x18000911a  jnz     loc_1800091F2
0x180009120  test    byte ptr [rcx+4], 2
0x180009124  jnz     loc_1800091C3
0x18000912a  mov     rcx, [rcx+8]
0x18000912e  xor     r8d, r8d
0x180009131  xor     edx, edx
0x180009133  test    byte ptr [rbx+4], 1
0x180009137  jz      short loc_180009164
0x180009139  call    cs:__imp_EfsDllOefsReleaseExclusiveOperation
0x18000913f  test    eax, eax
0x180009141  jns     short loc_180009160
0x180009143  mov     [rsp+58h+var_38], 245h
0x18000914b  mov     r9d, 0Bh
0x180009151  mov     r8d, eax
0x180009154  lea     rdx, EFS_API_ERROR
0x18000915b  call    fnEfsLogTrace1
0x180009160  xor     edx, edx
0x180009162  jmp     short loc_1800091B1
0x180009164  call    cs:__imp_EfsDllOefsReleaseExclusiveOperation
0x18000916a  test    eax, eax
0x18000916c  jns     short loc_18000918B
0x18000916e  mov     [rsp+58h+var_38], 260h
0x180009176  mov     r9d, 0Bh
0x18000917c  mov     r8d, eax
0x18000917f  lea     rdx, EFS_API_ERROR
0x180009186  call    fnEfsLogTrace1
0x18000918b  mov     rax, [rbx+18h]
0x18000918f  mov     qword ptr [rsp+58h+var_18+8], rax
0x180009194  mov     rax, [rbx+20h]
0x180009198  mov     qword ptr [rsp+58h+var_28+8], rax
0x18000919d  mov     eax, [rbx+10h]
0x1800091a0  mov     dword ptr [rsp+58h+var_28], eax
0x1800091a4  mov     qword ptr [rsp+58h+var_18], 0
0x1800091ad  mov     rdx, [rbx+28h]
0x1800091b1  mov     r8, [rbx+8]
0x1800091b5  lea     rcx, [rsp+58h+var_28]
0x1800091ba  call    CleanupOpenFileStreams
0x1800091bf  or      dword ptr [rbx+4], 2
0x1800091c3  call    cs:__imp_GetProcessHeap
0x1800091c9  mov     rcx, rax; hHeap
0x1800091cc  mov     r8, rbx; lpMem
0x1800091cf  xor     edx, edx; dwFlags
0x1800091d1  call    cs:__imp_HeapFree
0x1800091d7  mov     [rsp+58h+arg_0], 0
0x1800091e0  jmp     short loc_1800091F2
0x1800091e2  mov     rax, [rsp+58h+arg_0]
0x1800091e7  test    rax, rax
0x1800091ea  jz      short loc_1800091F2
0x1800091ec  mov     dword ptr [rax], 0
0x1800091f2  add     rsp, 50h
0x1800091f6  pop     rbx
0x1800091f7  retn
```
