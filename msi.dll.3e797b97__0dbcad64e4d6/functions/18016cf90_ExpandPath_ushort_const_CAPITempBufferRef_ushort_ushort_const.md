# ExpandPath(ushort const *,CAPITempBufferRef<ushort> &,ushort const *)

- ea: `0x18016cf90`
- end: `0x18016d1d6`
- name: `?ExpandPath@@YA?AW4Bool@@PEBGAEAV?$CAPITempBufferRef@G@@0@Z`
- size: `582`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x18004dcac`
- `0x1800640c0`
- `0x1800ca70c`
- `0x180140058`
- `0x1801503ac`
- `0x180156410`
- `0x18016c588`
- `0x18016d4ec`
- `0x1801d7880`

## callees

- `0x180014160`
- `0x1800141e0`
- `0x180062158`
- `0x18006cb7c`
- `0x18009fdf0`
- `0x18016cf90`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18016cfe1`
- `KERNEL32!lstrlenW` at `0x18016d043`
- `KERNEL32!lstrlenW` at `0x18016d14f`
- `KERNEL32!lstrlenW` at `0x18016cfe1`
- `KERNEL32!lstrlenW` at `0x18016d043`
- `KERNEL32!lstrlenW` at `0x18016d14f`
- `KERNEL32!GlobalFree` at `0x18016d0fc`
- `KERNEL32!GlobalFree` at `0x18016d1c3`
- `KERNEL32!GlobalFree` at `0x18016d0fc`
- `KERNEL32!GlobalFree` at `0x18016d1c3`
- `KERNEL32!GetCurrentDirectoryW` at `0x18016d05b`
- `KERNEL32!GetCurrentDirectoryW` at `0x18016d097`
- `KERNEL32!GetCurrentDirectoryW` at `0x18016d05b`
- `KERNEL32!GetCurrentDirectoryW` at `0x18016d097`

## pseudocode

```c
_BOOL8 __fastcall ExpandPath(unsigned __int16 *a1, __int64 a2, LPWSTR a3)
{
  _BOOL8 result; // rax
  unsigned int v7; // r15d
  DWORD v8; // esi
  DWORD CurrentDirectoryW; // eax
  int v10; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h] BYREF
  DWORD nBufferLength; // [rsp+28h] [rbp-D8h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  if ( !a1 )
  {
    result = 1;
    **(_WORD **)a2 = 0;
    return result;
  }
  v7 = lstrlenW(a1) + 1;
  if ( (unsigned int)PathType(a1) != 3 )
  {
    nBufferLength = 260;
    lpBuffer = Buffer;
    if ( a3 && *a3 )
    {
      v8 = lstrlenW(a3);
    }
    else
    {
      CurrentDirectoryW = GetCurrentDirectoryW(0x104u, Buffer);
      v8 = CurrentDirectoryW;
      if ( !CurrentDirectoryW )
        goto LABEL_25;
      if ( CurrentDirectoryW > nBufferLength )
      {
        if ( !(unsigned __int8)CAPITempBuffer<unsigned short,260>::SetSize(&lpBuffer, CurrentDirectoryW, 0) )
          goto LABEL_25;
        v8 = GetCurrentDirectoryW(nBufferLength, lpBuffer);
        if ( !v8 )
          goto LABEL_25;
      }
      a3 = lpBuffer;
    }
    if ( *a1 == 92 )
    {
      if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a2, v7 + 2, 0) )
      {
        **(_WORD **)a2 = *a3;
        *(_WORD *)(*(_QWORD *)a2 + 2LL) = a3[1];
        *(_WORD *)(*(_QWORD *)a2 + 4LL) = 0;
LABEL_17:
        if ( (int)nBufferLength > 260 )
          GlobalFree(lpBuffer);
        return (int)StringCchCatW(*(unsigned __int16 **)a2, *(int *)(a2 + 8), a1) >= 0;
      }
    }
    else
    {
      v10 = lstrlenW(a3);
      if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a2, v10 + v7 + 2, 0)
        && (int)StringCchCopyW(*(unsigned __int16 **)a2, *(int *)(a2 + 8), a3) >= 0
        && (!v8 || a3[v8 - 1] == 92 || (int)StringCchCatW(*(unsigned __int16 **)a2, *(int *)(a2 + 8), L"\\") >= 0) )
      {
        goto LABEL_17;
      }
    }
LABEL_25:
    if ( (int)nBufferLength > 260 )
      GlobalFree(lpBuffer);
    return 0;
  }
  if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a2, v7, 0) )
  {
    **(_WORD **)a2 = 0;
    return (int)StringCchCatW(*(unsigned __int16 **)a2, *(int *)(a2 + 8), a1) >= 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18016cf90  mov     [rsp-8+arg_18], rbx
0x18016cf95  push    rbp
0x18016cf96  push    rsi
0x18016cf97  push    rdi
0x18016cf98  push    r12
0x18016cf9a  push    r13
0x18016cf9c  push    r14
0x18016cf9e  push    r15
0x18016cfa0  lea     rbp, [rsp-150h]
0x18016cfa8  sub     rsp, 250h
0x18016cfaf  mov     rax, cs:__security_cookie
0x18016cfb6  xor     rax, rsp
0x18016cfb9  mov     [rbp+180h+var_40], rax
0x18016cfc0  xor     r12d, r12d
0x18016cfc3  mov     rdi, r8
0x18016cfc6  mov     rbx, rdx
0x18016cfc9  mov     r14, rcx
0x18016cfcc  test    rcx, rcx
0x18016cfcf  jnz     short loc_18016CFE1
0x18016cfd1  mov     rcx, [rdx]; lpString
0x18016cfd4  lea     eax, [r14+1]
0x18016cfd8  mov     [rcx], r12w
0x18016cfdc  jmp     loc_18016D121
0x18016cfe1  call    cs:__imp_lstrlenW
0x18016cfe8  nop     dword ptr [rax+rax+00h]
0x18016cfed  mov     rcx, r14
0x18016cff0  lea     r15d, [rax+1]
0x18016cff4  call    ?PathType@@YA?AW4iptEnum@@PEBG@Z; PathType(ushort const *)
0x18016cff9  cmp     eax, 3
0x18016cffc  jnz     short loc_18016D020
0x18016cffe  xor     r8d, r8d
0x18016d001  mov     edx, r15d
0x18016d004  mov     rcx, rbx
0x18016d007  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x18016d00c  test    al, al
0x18016d00e  jz      loc_18016D1CF
0x18016d014  mov     rcx, [rbx]
0x18016d017  mov     [rcx], r12w
0x18016d01b  jmp     loc_18016D108
0x18016d020  lea     rax, [rsp+280h+Buffer]
0x18016d025  mov     r13d, 104h
0x18016d02b  mov     [rsp+280h+nBufferLength], r13d
0x18016d030  mov     [rsp+280h+lpBuffer], rax
0x18016d035  test    rdi, rdi
0x18016d038  jz      short loc_18016D053
0x18016d03a  cmp     [rdi], r12w
0x18016d03e  jz      short loc_18016D053
0x18016d040  mov     rcx, rdi; lpString
0x18016d043  call    cs:__imp_lstrlenW
0x18016d04a  nop     dword ptr [rax+rax+00h]
0x18016d04f  mov     esi, eax
0x18016d051  jmp     short loc_18016D0B2
0x18016d053  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18016d058  mov     ecx, r13d; nBufferLength
0x18016d05b  call    cs:__imp_GetCurrentDirectoryW
0x18016d062  nop     dword ptr [rax+rax+00h]
0x18016d067  mov     esi, eax
0x18016d069  test    eax, eax
0x18016d06b  jz      loc_18016D1B7
0x18016d071  cmp     eax, [rsp+280h+nBufferLength]
0x18016d075  jbe     short loc_18016D0AD
0x18016d077  xor     r8d, r8d
0x18016d07a  lea     rcx, [rsp+280h+lpBuffer]
0x18016d07f  mov     edx, eax
0x18016d081  call    ?SetSize@?$CAPITempBuffer@G$0BAE@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,260>::SetSize(int,bool)
0x18016d086  test    al, al
0x18016d088  jz      loc_18016D1B7
0x18016d08e  mov     rdx, [rsp+280h+lpBuffer]; lpBuffer
0x18016d093  mov     ecx, [rsp+280h+nBufferLength]; nBufferLength
0x18016d097  call    cs:__imp_GetCurrentDirectoryW
0x18016d09e  nop     dword ptr [rax+rax+00h]
0x18016d0a3  mov     esi, eax
0x18016d0a5  test    eax, eax
0x18016d0a7  jz      loc_18016D1B7
0x18016d0ad  mov     rdi, [rsp+280h+lpBuffer]
0x18016d0b2  cmp     word ptr [r14], 5Ch ; '\'
0x18016d0b7  jnz     loc_18016D14C
0x18016d0bd  lea     edx, [r15+2]
0x18016d0c1  xor     r8d, r8d
0x18016d0c4  mov     rcx, rbx
0x18016d0c7  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x18016d0cc  test    al, al
0x18016d0ce  jz      loc_18016D1B7
0x18016d0d4  mov     rcx, [rbx]
0x18016d0d7  movzx   eax, word ptr [rdi]
0x18016d0da  mov     [rcx], ax
0x18016d0dd  mov     rcx, [rbx]
0x18016d0e0  movzx   eax, word ptr [rdi+2]
0x18016d0e4  mov     [rcx+2], ax
0x18016d0e8  mov     rcx, [rbx]
0x18016d0eb  mov     [rcx+4], r12w
0x18016d0f0  cmp     [rsp+280h+nBufferLength], r13d
0x18016d0f5  jle     short loc_18016D108
0x18016d0f7  mov     rcx, [rsp+280h+lpBuffer]; hMem
0x18016d0fc  call    cs:__imp_GlobalFree
0x18016d103  nop     dword ptr [rax+rax+00h]
0x18016d108  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x18016d10c  mov     r8, r14; unsigned __int16 *
0x18016d10f  mov     rcx, [rbx]; unsigned __int16 *
0x18016d112  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18016d117  test    eax, eax
0x18016d119  mov     ecx, r12d
0x18016d11c  setns   cl
0x18016d11f  mov     eax, ecx
0x18016d121  mov     rcx, [rbp+180h+var_40]
0x18016d128  xor     rcx, rsp; StackCookie
0x18016d12b  call    __security_check_cookie
0x18016d130  mov     rbx, [rsp+280h+arg_18]
0x18016d138  add     rsp, 250h
0x18016d13f  pop     r15
0x18016d141  pop     r14
0x18016d143  pop     r13
0x18016d145  pop     r12
0x18016d147  pop     rdi
0x18016d148  pop     rsi
0x18016d149  pop     rbp
0x18016d14a  retn
0x18016d14c  mov     rcx, rdi; lpString
0x18016d14f  call    cs:__imp_lstrlenW
0x18016d156  nop     dword ptr [rax+rax+00h]
0x18016d15b  lea     edx, [r15+2]
0x18016d15f  xor     r8d, r8d
0x18016d162  add     edx, eax
0x18016d164  mov     rcx, rbx
0x18016d167  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x18016d16c  test    al, al
0x18016d16e  jz      short loc_18016D1B7
0x18016d170  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x18016d174  mov     r8, rdi; unsigned __int16 *
0x18016d177  mov     rcx, [rbx]; unsigned __int16 *
0x18016d17a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18016d17f  test    eax, eax
0x18016d181  js      short loc_18016D1B7
0x18016d183  test    esi, esi
0x18016d185  jz      loc_18016D0F0
0x18016d18b  lea     eax, [rsi-1]
0x18016d18e  movsxd  rcx, eax
0x18016d191  cmp     word ptr [rdi+rcx*2], 5Ch ; '\'
0x18016d196  jz      loc_18016D0F0
0x18016d19c  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x18016d1a0  lea     r8, asc_18027979C; "\\"
0x18016d1a7  mov     rcx, [rbx]; unsigned __int16 *
0x18016d1aa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18016d1af  test    eax, eax
0x18016d1b1  jns     loc_18016D0F0
0x18016d1b7  cmp     [rsp+280h+nBufferLength], r13d
0x18016d1bc  jle     short loc_18016D1CF
0x18016d1be  mov     rcx, [rsp+280h+lpBuffer]; hMem
0x18016d1c3  call    cs:__imp_GlobalFree
0x18016d1ca  nop     dword ptr [rax+rax+00h]
0x18016d1cf  xor     eax, eax
0x18016d1d1  jmp     loc_18016D121
```
