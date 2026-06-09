# DDMAdminServerGetInfo

- ea: `0x180004730`
- end: `0x180004946`
- name: `DDMAdminServerGetInfo`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004730`
- `0x18003b8b0`
- `0x18003b8f4`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800047cf`
- `KERNEL32!HeapAlloc` at `0x1800047cf`
- `KERNEL32!LeaveCriticalSection` at `0x180004933`
- `KERNEL32!LeaveCriticalSection` at `0x180004933`
- `KERNEL32!EnterCriticalSection` at `0x180004908`
- `KERNEL32!EnterCriticalSection` at `0x180004908`
- `KERNEL32!HeapFree` at `0x180004815`
- `KERNEL32!HeapFree` at `0x1800048f6`
- `KERNEL32!HeapFree` at `0x180004815`
- `KERNEL32!HeapFree` at `0x1800048f6`
- `rasman!RasGetDeviceConfigInfo` at `0x18000473b`

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
  if ( dword_1800C8654 )
    v2 = DdmGetDeviceConfigInfo;
  if ( !a2 )
  {
    *a1 = 0;
    EnterCriticalSection(&gblDeviceTable);
    Instance = DdmDeviceTable::GetInstance(0x11u);
    a1[2] = DdmDeviceTable::GetDeviceCount(Instance);
    a1[3] = dword_1800C84B0;
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
0x180004730  push    rbx
0x180004732  push    rbp
0x180004733  push    rsi
0x180004734  push    rdi
0x180004735  push    r14
0x180004737  sub     rsp, 30h
0x18000473b  mov     rsi, cs:__imp_RasGetDeviceConfigInfo
0x180004742  lea     rax, DdmGetDeviceConfigInfo
0x180004749  xor     r14d, r14d
0x18000474c  mov     ebp, edx
0x18000474e  cmp     cs:dword_1800C8654, r14d
0x180004755  mov     rbx, rcx
0x180004758  cmovnz  rsi, rax
0x18000475c  test    edx, edx
0x18000475e  jz      loc_1800048FE
0x180004764  lea     eax, [rdx-1]
0x180004767  cmp     eax, 1
0x18000476a  jbe     short loc_180004775
0x18000476c  lea     eax, [r14+32h]
0x180004770  jmp     loc_18000493B
0x180004775  lea     r9, [rsp+58h+dwBytes]
0x18000477a  mov     [rsp+58h+arg_10], r14d
0x18000477f  lea     r8, [rsp+58h+arg_10]
0x180004784  mov     dword ptr [rsp+58h+dwBytes], r14d
0x180004789  lea     rdx, [rsp+58h+arg_18]
0x18000478e  mov     [rsp+58h+arg_18], 6
0x180004796  xor     ecx, ecx
0x180004798  mov     [rsp+58h+var_38], r14
0x18000479d  mov     rax, rsi
0x1800047a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a5  test    eax, eax
0x1800047a7  jnz     short loc_1800047B3
0x1800047a9  mov     eax, 10DFh
0x1800047ae  jmp     loc_18000493B
0x1800047b3  cmp     eax, 25Bh
0x1800047b8  jnz     loc_18000493B
0x1800047be  mov     r8d, dword ptr [rsp+58h+dwBytes]; dwBytes
0x1800047c3  mov     edx, 8; dwFlags
0x1800047c8  mov     rcx, cs:hHeap; hHeap
0x1800047cf  call    cs:__imp_HeapAlloc
0x1800047d5  mov     rdi, rax
0x1800047d8  test    rax, rax
0x1800047db  jnz     short loc_1800047E5
0x1800047dd  lea     eax, [rdi+8]
0x1800047e0  jmp     loc_18000493B
0x1800047e5  lea     r9, [rsp+58h+dwBytes]
0x1800047ea  mov     [rsp+58h+var_38], rdi
0x1800047ef  lea     r8, [rsp+58h+arg_10]
0x1800047f4  xor     ecx, ecx
0x1800047f6  lea     rdx, [rsp+58h+arg_18]
0x1800047fb  mov     rax, rsi
0x1800047fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004803  mov     esi, eax
0x180004805  test    eax, eax
0x180004807  jz      short loc_180004822
0x180004809  mov     rcx, cs:hHeap; hHeap
0x180004810  mov     r8, rdi; lpMem
0x180004813  xor     edx, edx; dwFlags
0x180004815  call    cs:__imp_HeapFree
0x18000481b  mov     eax, esi
0x18000481d  jmp     loc_18000493B
0x180004822  mov     eax, ebp
0x180004824  sub     eax, 1
0x180004827  jz      short loc_180004832
0x180004829  cmp     eax, 1
0x18000482c  jnz     short loc_180004839
0x18000482e  mov     [rbx+10h], r14
0x180004832  mov     [rbx+8], r14
0x180004836  mov     [rbx], r14
0x180004839  mov     r8d, [rsp+58h+arg_10]
0x18000483e  mov     edx, r14d
0x180004841  test    r8d, r8d
0x180004844  jz      loc_1800048EA
0x18000484a  mov     eax, ebp
0x18000484c  sub     eax, 1
0x18000484f  jz      short loc_18000488A
0x180004851  cmp     eax, 1
0x180004854  jnz     loc_1800048DF
0x18000485a  mov     eax, edx
0x18000485c  imul    rcx, rax, 1D8h
0x180004863  cmp     word ptr [rcx+rdi+30h], 0Eh
0x180004869  jnz     short loc_18000488A
0x18000486b  mov     eax, [rcx+rdi+1Ch]
0x18000486f  mov     [rbx+10h], eax
0x180004872  cmp     [rcx+rdi+8], r14d
0x180004877  jz      short loc_18000487D
0x180004879  or      dword ptr [rbx+14h], 1
0x18000487d  cmp     [rcx+rdi+0Ch], r14d
0x180004882  jz      short loc_1800048DF
0x180004884  or      dword ptr [rbx+14h], 2
0x180004888  jmp     short loc_1800048DF
0x18000488a  mov     eax, edx
0x18000488c  imul    rcx, rax, 1D8h
0x180004893  mov     eax, [rcx+rdi+30h]
0x180004897  movzx   eax, ax
0x18000489a  cmp     eax, 8
0x18000489d  jnz     short loc_1800048BD
0x18000489f  mov     eax, [rcx+rdi+1Ch]
0x1800048a3  mov     [rbx], eax
0x1800048a5  cmp     [rcx+rdi+8], r14d
0x1800048aa  jz      short loc_1800048B0
0x1800048ac  or      dword ptr [rbx+4], 1
0x1800048b0  cmp     [rcx+rdi+0Ch], r14d
0x1800048b5  jz      short loc_1800048DF
0x1800048b7  or      dword ptr [rbx+4], 2
0x1800048bb  jmp     short loc_1800048DF
0x1800048bd  cmp     eax, 9
0x1800048c0  jnz     short loc_1800048DF
0x1800048c2  mov     eax, [rcx+rdi+1Ch]
0x1800048c6  mov     [rbx+8], eax
0x1800048c9  cmp     [rcx+rdi+8], r14d
0x1800048ce  jz      short loc_1800048D4
0x1800048d0  or      dword ptr [rbx+0Ch], 1
0x1800048d4  cmp     [rcx+rdi+0Ch], r14d
0x1800048d9  jz      short loc_1800048DF
0x1800048db  or      dword ptr [rbx+0Ch], 2
0x1800048df  inc     edx
0x1800048e1  cmp     edx, r8d
0x1800048e4  jb      loc_18000484A
0x1800048ea  mov     rcx, cs:hHeap; hHeap
0x1800048f1  mov     r8, rdi; lpMem
0x1800048f4  xor     edx, edx; dwFlags
0x1800048f6  call    cs:__imp_HeapFree
0x1800048fc  jmp     short loc_180004939
0x1800048fe  mov     [rcx], r14d
0x180004901  lea     rcx, gblDeviceTable; lpCriticalSection
0x180004908  call    cs:__imp_EnterCriticalSection
0x18000490e  mov     ecx, 11h; unsigned int
0x180004913  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180004918  mov     rcx, rax; this
0x18000491b  call    ?GetDeviceCount@DdmDeviceTable@@QEAAKXZ; DdmDeviceTable::GetDeviceCount(void)
0x180004920  mov     [rbx+8], eax
0x180004923  lea     rcx, gblDeviceTable; lpCriticalSection
0x18000492a  mov     eax, cs:dword_1800C84B0
0x180004930  mov     [rbx+0Ch], eax
0x180004933  call    cs:__imp_LeaveCriticalSection
0x180004939  xor     eax, eax
0x18000493b  add     rsp, 30h
0x18000493f  pop     r14
0x180004941  pop     rdi
0x180004942  pop     rsi
0x180004943  pop     rbp
0x180004944  pop     rbx
0x180004945  retn
```
