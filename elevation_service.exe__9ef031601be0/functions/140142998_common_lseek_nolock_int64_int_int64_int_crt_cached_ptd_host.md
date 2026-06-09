# common_lseek_nolock<__int64>(int,__int64,int,__crt_cached_ptd_host &)

- ea: `0x140142998`
- end: `0x140142a47`
- name: `??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z`
- size: `175`
- prototype: `union _LARGE_INTEGER __fastcall(int, LARGE_INTEGER, DWORD, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140142560`
- `0x1401425fc`
- `0x1401427ec`

## callees

- `0x14013fe48`
- `0x140140e18`
- `0x140142998`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401429f4`
- `KERNEL32!GetLastError` at `0x1401429f4`
- `KERNEL32!SetFilePointerEx` at `0x1401429ea`
- `KERNEL32!SetFilePointerEx` at `0x1401429ea`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock<__int64>(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  union _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (union _LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return (union _LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (union _LARGE_INTEGER)-1LL;
  *(_BYTE *)(qword_14038C5D0[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x140142998  mov     [rsp+arg_0], rbx
0x14014299d  mov     [rsp+arg_8], rbp
0x1401429a2  mov     [rsp+arg_10], rsi
0x1401429a7  push    rdi
0x1401429a8  sub     rsp, 30h
0x1401429ac  movsxd  rdi, ecx
0x1401429af  mov     rbx, r9
0x1401429b2  mov     ecx, edi; FileHandle
0x1401429b4  mov     esi, r8d
0x1401429b7  mov     rbp, rdx
0x1401429ba  call    _get_osfhandle
0x1401429bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401429c3  jnz     short loc_1401429D6
0x1401429c5  mov     byte ptr [rbx+30h], 1
0x1401429c9  mov     dword ptr [rbx+2Ch], 9
0x1401429d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401429d4  jmp     short loc_140142A32
0x1401429d6  and     qword ptr [rsp+38h+NewFilePointer], 0
0x1401429dc  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x1401429e1  mov     r9d, esi; dwMoveMethod
0x1401429e4  mov     rdx, rbp; liDistanceToMove
0x1401429e7  mov     rcx, rax; hFile
0x1401429ea  call    cs:SetFilePointerEx
0x1401429f0  test    eax, eax
0x1401429f2  jnz     short loc_140142A06
0x1401429f4  call    cs:__imp_GetLastError
0x1401429fa  mov     ecx, eax
0x1401429fc  mov     rdx, rbx
0x1401429ff  call    __acrt_errno_map_os_error_ptd
0x140142a04  jmp     short loc_1401429D0
0x140142a06  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x140142a0b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140142a0f  jz      short loc_1401429D0
0x140142a11  mov     rdx, rdi
0x140142a14  lea     r8, qword_14038C5D0
0x140142a1b  and     edx, 3Fh
0x140142a1e  mov     rcx, rdi
0x140142a21  sar     rcx, 6
0x140142a25  lea     rdx, [rdx+rdx*8]
0x140142a29  mov     rcx, [r8+rcx*8]
0x140142a2d  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x140142a32  mov     rbx, [rsp+38h+arg_0]
0x140142a37  mov     rbp, [rsp+38h+arg_8]
0x140142a3c  mov     rsi, [rsp+38h+arg_10]
0x140142a41  add     rsp, 30h
0x140142a45  pop     rdi
0x140142a46  retn
```
