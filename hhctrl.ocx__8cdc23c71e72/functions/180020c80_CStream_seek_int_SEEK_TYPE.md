# CStream::seek(int,SEEK_TYPE)

- ea: `0x180020c80`
- end: `0x180020d9e`
- name: `?seek@CStream@@QEAAHHW4SEEK_TYPE@@@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c074`

## callees

- `0x180020b78`
- `0x180020c80`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180020d5e`
- `KERNEL32!ReleaseSemaphore` at `0x180020d7b`
- `KERNEL32!ReleaseSemaphore` at `0x180020d5e`
- `KERNEL32!ReleaseSemaphore` at `0x180020d7b`
- `KERNEL32!_lread` at `0x180020d10`
- `KERNEL32!_lread` at `0x180020d10`
- `KERNEL32!_llseek` at `0x180020cfc`
- `KERNEL32!_llseek` at `0x180020cfc`

## pseudocode

```c
__int64 __fastcall CStream::seek(__int64 a1, int a2)
{
  int v2; // r9d
  unsigned int *v3; // rdi
  LONG v5; // esi
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  LONG v9; // eax
  UINT v10; // r8d
  void *v11; // rdx
  HFILE v12; // ecx
  signed int v13; // eax
  signed int v14; // esi
  bool v15; // zf
  __int64 v16; // rcx
  HANDLE v17; // rcx

  v2 = *(_DWORD *)(a1 + 36);
  v3 = (unsigned int *)(a1 + 32);
  v5 = *(_DWORD *)(a1 + 8) + a2 + v2 - *(_DWORD *)(a1 + 40);
  if ( v5 < v2 || v5 >= (int)*v3 )
  {
    if ( *(_DWORD *)(a1 + 76) )
      CStream::WaitForReadAhead((CStream *)a1);
    v9 = _llseek(*(_DWORD *)(a1 + 28), v5, 0);
    v10 = *(_DWORD *)(a1 + 56);
    v11 = *(void **)(a1 + 40);
    v12 = *(_DWORD *)(a1 + 28);
    *(_DWORD *)(a1 + 36) = v9;
    v13 = _lread(v12, v11, v10);
    v14 = v13;
    if ( v13 == -1 )
    {
      *(_DWORD *)(a1 + 24) = 1;
      return 255;
    }
    else
    {
      v15 = *(_DWORD *)(a1 + 76) == 0;
      *v3 = v13 + *(_DWORD *)(a1 + 36);
      v16 = *(_QWORD *)(a1 + 40);
      *(_QWORD *)(a1 + 8) = v16;
      *(_QWORD *)(a1 + 16) = v16 + v13;
      if ( !v15 )
      {
        v17 = hSemaphore;
        *(_DWORD *)(a1 + 60) = -2;
        ReleaseSemaphore(v17, 1, 0);
        if ( dword_18008C21C )
          ReleaseSemaphore(hHandle, 1, 0);
      }
      if ( !v14 )
        *(_DWORD *)(a1 + 24) = 1;
      return *v3;
    }
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 40);
    v7 = v6 + v5 - v2;
    *(_QWORD *)(a1 + 8) = v7;
    if ( v7 >= *(_QWORD *)(a1 + 16) && *(_QWORD *)(a1 + 16) < (unsigned __int64)(v6 + *(int *)(a1 + 56)) )
      *(_DWORD *)(a1 + 24) = 1;
    return (unsigned int)(*(_DWORD *)(a1 + 8) + v2 - *(_DWORD *)(a1 + 40));
  }
}

```

## disassembly

```asm
0x180020c80  mov     [rsp+arg_0], rbx
0x180020c85  mov     [rsp+arg_8], rsi
0x180020c8a  push    rdi
0x180020c8b  sub     rsp, 20h
0x180020c8f  mov     r9d, [rcx+24h]
0x180020c93  lea     rdi, [rcx+20h]
0x180020c97  mov     esi, r9d
0x180020c9a  mov     rbx, rcx
0x180020c9d  sub     esi, [rcx+28h]
0x180020ca0  add     esi, edx
0x180020ca2  add     esi, [rcx+8]
0x180020ca5  cmp     esi, r9d
0x180020ca8  jl      short loc_180020CE9
0x180020caa  cmp     esi, [rdi]
0x180020cac  jge     short loc_180020CE9
0x180020cae  mov     rdx, [rcx+28h]
0x180020cb2  sub     esi, r9d
0x180020cb5  movsxd  rcx, esi
0x180020cb8  add     rcx, rdx
0x180020cbb  mov     [rbx+8], rcx
0x180020cbf  cmp     rcx, [rbx+10h]
0x180020cc3  jb      short loc_180020CD9
0x180020cc5  movsxd  rcx, dword ptr [rbx+38h]
0x180020cc9  add     rcx, rdx; this
0x180020ccc  cmp     [rbx+10h], rcx
0x180020cd0  jnb     short loc_180020CD9
0x180020cd2  mov     dword ptr [rbx+18h], 1
0x180020cd9  sub     r9d, [rbx+28h]
0x180020cdd  add     r9d, [rbx+8]
0x180020ce1  mov     eax, r9d
0x180020ce4  jmp     loc_180020D8E
0x180020ce9  cmp     dword ptr [rcx+4Ch], 0
0x180020ced  jz      short loc_180020CF4
0x180020cef  call    ?WaitForReadAhead@CStream@@IEAAXXZ; CStream::WaitForReadAhead(void)
0x180020cf4  mov     ecx, [rbx+1Ch]; hFile
0x180020cf7  xor     r8d, r8d; iOrigin
0x180020cfa  mov     edx, esi; lOffset
0x180020cfc  call    cs:__imp__llseek
0x180020d02  mov     r8d, [rbx+38h]; uBytes
0x180020d06  mov     rdx, [rbx+28h]; lpBuffer
0x180020d0a  mov     ecx, [rbx+1Ch]; hFile
0x180020d0d  mov     [rbx+24h], eax
0x180020d10  call    cs:__imp__lread
0x180020d16  movsxd  rsi, eax
0x180020d19  cmp     esi, 0FFFFFFFFh
0x180020d1c  jnz     short loc_180020D2C
0x180020d1e  mov     dword ptr [rbx+18h], 1
0x180020d25  mov     eax, 0FFh
0x180020d2a  jmp     short loc_180020D8E
0x180020d2c  mov     ecx, [rbx+24h]
0x180020d2f  add     ecx, esi
0x180020d31  cmp     dword ptr [rbx+4Ch], 0
0x180020d35  mov     [rdi], ecx
0x180020d37  mov     rcx, [rbx+28h]
0x180020d3b  mov     [rbx+8], rcx
0x180020d3f  lea     rax, [rcx+rsi]
0x180020d43  mov     [rbx+10h], rax
0x180020d47  jz      short loc_180020D81
0x180020d49  mov     rcx, cs:hSemaphore; hSemaphore
0x180020d50  xor     r8d, r8d; lpPreviousCount
0x180020d53  mov     dword ptr [rbx+3Ch], 0FFFFFFFEh
0x180020d5a  lea     edx, [r8+1]; lReleaseCount
0x180020d5e  call    cs:__imp_ReleaseSemaphore
0x180020d64  cmp     cs:dword_18008C21C, 0
0x180020d6b  jz      short loc_180020D81
0x180020d6d  mov     rcx, cs:hHandle; hSemaphore
0x180020d74  xor     r8d, r8d; lpPreviousCount
0x180020d77  lea     edx, [r8+1]; lReleaseCount
0x180020d7b  call    cs:__imp_ReleaseSemaphore
0x180020d81  test    esi, esi
0x180020d83  jnz     short loc_180020D8C
0x180020d85  mov     dword ptr [rbx+18h], 1
0x180020d8c  mov     eax, [rdi]
0x180020d8e  mov     rbx, [rsp+28h+arg_0]
0x180020d93  mov     rsi, [rsp+28h+arg_8]
0x180020d98  add     rsp, 20h
0x180020d9c  pop     rdi
0x180020d9d  retn
```
