# DDMAdminServerGetInfo

- ea: `0x180004920`
- end: `0x180004b55`
- name: `DDMAdminServerGetInfo`
- size: `565`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004920`
- `0x18003d230`
- `0x18003d278`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800049bf`
- `KERNEL32!HeapAlloc` at `0x1800049bf`
- `KERNEL32!LeaveCriticalSection` at `0x180004b3b`
- `KERNEL32!LeaveCriticalSection` at `0x180004b3b`
- `KERNEL32!EnterCriticalSection` at `0x180004b0a`
- `KERNEL32!EnterCriticalSection` at `0x180004b0a`
- `KERNEL32!HeapFree` at `0x180004a0b`
- `KERNEL32!HeapFree` at `0x180004af2`
- `KERNEL32!HeapFree` at `0x180004a0b`
- `KERNEL32!HeapFree` at `0x180004af2`
- `rasman!RasGetDeviceConfigInfo` at `0x18000492b`

## pseudocode

```c
__int64 __fastcall DDMAdminServerGetInfo(_DWORD *a1, int a2)
{
  __int64 (__fastcall *v2)(int, int, int, int, void *); // rsi
  __int64 result; // rax
  char *v6; // rax
  char *v7; // rdi
  unsigned int v8; // esi
  unsigned int v9; // r8d
  unsigned int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  DdmDeviceTable *Instance; // rax
  SIZE_T dwBytes; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+18h] BYREF
  int v17; // [rsp+78h] [rbp+20h] BYREF

  v2 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  if ( dword_1800CF654 )
    v2 = DdmGetDeviceConfigInfo;
  if ( !a2 )
  {
    *a1 = 0;
    EnterCriticalSection(&gblDeviceTable);
    Instance = DdmDeviceTable::GetInstance(0x11u);
    a1[2] = DdmDeviceTable::GetDeviceCount(Instance);
    a1[3] = dword_1800CF4B0;
    LeaveCriticalSection(&gblDeviceTable);
    return 0;
  }
  if ( (unsigned int)(a2 - 1) > 1 )
    return 50;
  v16 = 0;
  LODWORD(dwBytes) = 0;
  v17 = 6;
  result = v2(0, (int)&v17, (int)&v16, (int)&dwBytes, 0);
  if ( !(_DWORD)result )
    return 4319;
  if ( (_DWORD)result == 603 )
  {
    v6 = (char *)HeapAlloc(hHeap, 8u, (unsigned int)dwBytes);
    v7 = v6;
    if ( !v6 )
      return 8;
    v8 = v2(0, (int)&v17, (int)&v16, (int)&dwBytes, v6);
    if ( v8 )
    {
      HeapFree(hHeap, 0, v7);
      return v8;
    }
    if ( a2 != 1 )
    {
      if ( a2 != 2 )
      {
LABEL_17:
        v9 = v16;
        v10 = 0;
        if ( v16 )
        {
          while ( a2 != 1 )
          {
            if ( a2 == 2 )
            {
              v11 = 472LL * v10;
              if ( *(_WORD *)&v7[v11 + 48] != 14 )
                break;
              a1[4] = *(_DWORD *)&v7[v11 + 28];
              if ( *(_DWORD *)&v7[v11 + 8] )
                a1[5] |= 1u;
              if ( *(_DWORD *)&v7[v11 + 12] )
                a1[5] |= 2u;
            }
LABEL_35:
            if ( ++v10 >= v9 )
              goto LABEL_36;
          }
          v12 = 472LL * v10;
          v13 = (unsigned __int16)*(_DWORD *)&v7[v12 + 48];
          if ( v13 == 8 )
          {
            *a1 = *(_DWORD *)&v7[v12 + 28];
            if ( *(_DWORD *)&v7[v12 + 8] )
              a1[1] |= 1u;
            if ( *(_DWORD *)&v7[v12 + 12] )
              a1[1] |= 2u;
          }
          else if ( v13 == 9 )
          {
            a1[2] = *(_DWORD *)&v7[v12 + 28];
            if ( *(_DWORD *)&v7[v12 + 8] )
              a1[3] |= 1u;
            if ( *(_DWORD *)&v7[v12 + 12] )
              a1[3] |= 2u;
          }
          goto LABEL_35;
        }
LABEL_36:
        HeapFree(hHeap, 0, v7);
        return 0;
      }
      *((_QWORD *)a1 + 2) = 0;
    }
    *((_QWORD *)a1 + 1) = 0;
    *(_QWORD *)a1 = 0;
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x180004920  push    rbx
0x180004922  push    rbp
0x180004923  push    rsi
0x180004924  push    rdi
0x180004925  push    r14
0x180004927  sub     rsp, 30h
0x18000492b  mov     rsi, cs:__imp_RasGetDeviceConfigInfo
0x180004932  lea     rax, DdmGetDeviceConfigInfo
0x180004939  xor     r14d, r14d
0x18000493c  mov     ebp, edx
0x18000493e  cmp     cs:dword_1800CF654, r14d
0x180004945  mov     rbx, rcx
0x180004948  cmovnz  rsi, rax
0x18000494c  test    edx, edx
0x18000494e  jz      loc_180004B00
0x180004954  lea     eax, [rdx-1]
0x180004957  cmp     eax, 1
0x18000495a  jbe     short loc_180004965
0x18000495c  lea     eax, [r14+32h]
0x180004960  jmp     loc_180004B49
0x180004965  lea     r9, [rsp+58h+dwBytes]
0x18000496a  mov     [rsp+58h+arg_10], r14d
0x18000496f  lea     r8, [rsp+58h+arg_10]
0x180004974  mov     dword ptr [rsp+58h+dwBytes], r14d
0x180004979  lea     rdx, [rsp+58h+arg_18]
0x18000497e  mov     [rsp+58h+arg_18], 6
0x180004986  xor     ecx, ecx
0x180004988  mov     [rsp+58h+var_38], r14
0x18000498d  mov     rax, rsi
0x180004990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004995  test    eax, eax
0x180004997  jnz     short loc_1800049A3
0x180004999  mov     eax, 10DFh
0x18000499e  jmp     loc_180004B49
0x1800049a3  cmp     eax, 25Bh
0x1800049a8  jnz     loc_180004B49
0x1800049ae  mov     r8d, dword ptr [rsp+58h+dwBytes]; dwBytes
0x1800049b3  mov     edx, 8; dwFlags
0x1800049b8  mov     rcx, cs:hHeap; hHeap
0x1800049bf  call    cs:__imp_HeapAlloc
0x1800049c6  nop     dword ptr [rax+rax+00h]
0x1800049cb  mov     rdi, rax
0x1800049ce  test    rax, rax
0x1800049d1  jnz     short loc_1800049DB
0x1800049d3  lea     eax, [rdi+8]
0x1800049d6  jmp     loc_180004B49
0x1800049db  lea     r9, [rsp+58h+dwBytes]
0x1800049e0  mov     [rsp+58h+var_38], rdi
0x1800049e5  lea     r8, [rsp+58h+arg_10]
0x1800049ea  xor     ecx, ecx
0x1800049ec  lea     rdx, [rsp+58h+arg_18]
0x1800049f1  mov     rax, rsi
0x1800049f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f9  mov     esi, eax
0x1800049fb  test    eax, eax
0x1800049fd  jz      short loc_180004A1E
0x1800049ff  mov     rcx, cs:hHeap; hHeap
0x180004a06  mov     r8, rdi; lpMem
0x180004a09  xor     edx, edx; dwFlags
0x180004a0b  call    cs:__imp_HeapFree
0x180004a12  nop     dword ptr [rax+rax+00h]
0x180004a17  mov     eax, esi
0x180004a19  jmp     loc_180004B49
0x180004a1e  mov     eax, ebp
0x180004a20  sub     eax, 1
0x180004a23  jz      short loc_180004A2E
0x180004a25  cmp     eax, 1
0x180004a28  jnz     short loc_180004A35
0x180004a2a  mov     [rbx+10h], r14
0x180004a2e  mov     [rbx+8], r14
0x180004a32  mov     [rbx], r14
0x180004a35  mov     r8d, [rsp+58h+arg_10]
0x180004a3a  mov     edx, r14d
0x180004a3d  test    r8d, r8d
0x180004a40  jz      loc_180004AE6
0x180004a46  mov     eax, ebp
0x180004a48  sub     eax, 1
0x180004a4b  jz      short loc_180004A86
0x180004a4d  cmp     eax, 1
0x180004a50  jnz     loc_180004ADB
0x180004a56  mov     eax, edx
0x180004a58  imul    rcx, rax, 1D8h
0x180004a5f  cmp     word ptr [rcx+rdi+30h], 0Eh
0x180004a65  jnz     short loc_180004A86
0x180004a67  mov     eax, [rcx+rdi+1Ch]
0x180004a6b  mov     [rbx+10h], eax
0x180004a6e  cmp     [rcx+rdi+8], r14d
0x180004a73  jz      short loc_180004A79
0x180004a75  or      dword ptr [rbx+14h], 1
0x180004a79  cmp     [rcx+rdi+0Ch], r14d
0x180004a7e  jz      short loc_180004ADB
0x180004a80  or      dword ptr [rbx+14h], 2
0x180004a84  jmp     short loc_180004ADB
0x180004a86  mov     eax, edx
0x180004a88  imul    rcx, rax, 1D8h
0x180004a8f  mov     eax, [rcx+rdi+30h]
0x180004a93  movzx   eax, ax
0x180004a96  cmp     eax, 8
0x180004a99  jnz     short loc_180004AB9
0x180004a9b  mov     eax, [rcx+rdi+1Ch]
0x180004a9f  mov     [rbx], eax
0x180004aa1  cmp     [rcx+rdi+8], r14d
0x180004aa6  jz      short loc_180004AAC
0x180004aa8  or      dword ptr [rbx+4], 1
0x180004aac  cmp     [rcx+rdi+0Ch], r14d
0x180004ab1  jz      short loc_180004ADB
0x180004ab3  or      dword ptr [rbx+4], 2
0x180004ab7  jmp     short loc_180004ADB
0x180004ab9  cmp     eax, 9
0x180004abc  jnz     short loc_180004ADB
0x180004abe  mov     eax, [rcx+rdi+1Ch]
0x180004ac2  mov     [rbx+8], eax
0x180004ac5  cmp     [rcx+rdi+8], r14d
0x180004aca  jz      short loc_180004AD0
0x180004acc  or      dword ptr [rbx+0Ch], 1
0x180004ad0  cmp     [rcx+rdi+0Ch], r14d
0x180004ad5  jz      short loc_180004ADB
0x180004ad7  or      dword ptr [rbx+0Ch], 2
0x180004adb  inc     edx
0x180004add  cmp     edx, r8d
0x180004ae0  jb      loc_180004A46
0x180004ae6  mov     rcx, cs:hHeap; hHeap
0x180004aed  mov     r8, rdi; lpMem
0x180004af0  xor     edx, edx; dwFlags
0x180004af2  call    cs:__imp_HeapFree
0x180004af9  nop     dword ptr [rax+rax+00h]
0x180004afe  jmp     short loc_180004B47
0x180004b00  mov     [rcx], r14d
0x180004b03  lea     rcx, gblDeviceTable; lpCriticalSection
0x180004b0a  call    cs:__imp_EnterCriticalSection
0x180004b11  nop     dword ptr [rax+rax+00h]
0x180004b16  mov     ecx, 11h; unsigned int
0x180004b1b  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180004b20  mov     rcx, rax; this
0x180004b23  call    ?GetDeviceCount@DdmDeviceTable@@QEAAKXZ; DdmDeviceTable::GetDeviceCount(void)
0x180004b28  mov     [rbx+8], eax
0x180004b2b  lea     rcx, gblDeviceTable; lpCriticalSection
0x180004b32  mov     eax, cs:dword_1800CF4B0
0x180004b38  mov     [rbx+0Ch], eax
0x180004b3b  call    cs:__imp_LeaveCriticalSection
0x180004b42  nop     dword ptr [rax+rax+00h]
0x180004b47  xor     eax, eax
0x180004b49  add     rsp, 30h
0x180004b4d  pop     r14
0x180004b4f  pop     rdi
0x180004b50  pop     rsi
0x180004b51  pop     rbp
0x180004b52  pop     rbx
0x180004b53  retn
```
