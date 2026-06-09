# ExpandPath(ushort const *,CAPITempBufferRef<ushort> &,ushort const *)

- ea: `0x180166ff0`
- end: `0x18016720b`
- name: `?ExpandPath@@YA?AW4Bool@@PEBGAEAV?$CAPITempBufferRef@G@@0@Z`
- size: `539`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x180086f20`
- `0x1800bca84`
- `0x1801123bc`
- `0x18013ae34`
- `0x18014cd9c`
- `0x180150ac0`
- `0x1801665f8`
- `0x18016751c`
- `0x1801cec3c`

## callees

- `0x180025560`
- `0x1800255e0`
- `0x180027f18`
- `0x180071fdc`
- `0x1800a9f70`
- `0x180166ff0`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180167041`
- `KERNEL32!lstrlenW` at `0x18016709d`
- `KERNEL32!lstrlenW` at `0x180167190`
- `KERNEL32!lstrlenW` at `0x180167041`
- `KERNEL32!lstrlenW` at `0x18016709d`
- `KERNEL32!lstrlenW` at `0x180167190`
- `KERNEL32!GlobalFree` at `0x180167144`
- `KERNEL32!GlobalFree` at `0x1801671fe`
- `KERNEL32!GlobalFree` at `0x180167144`
- `KERNEL32!GlobalFree` at `0x1801671fe`
- `KERNEL32!GetCurrentDirectoryW` at `0x1801670af`
- `KERNEL32!GetCurrentDirectoryW` at `0x1801670e5`
- `KERNEL32!GetCurrentDirectoryW` at `0x1801670af`
- `KERNEL32!GetCurrentDirectoryW` at `0x1801670e5`

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
0x180166ff0  mov     [rsp-8+arg_18], rbx
0x180166ff5  push    rbp
0x180166ff6  push    rsi
0x180166ff7  push    rdi
0x180166ff8  push    r12
0x180166ffa  push    r13
0x180166ffc  push    r14
0x180166ffe  push    r15
0x180167000  lea     rbp, [rsp-150h]
0x180167008  sub     rsp, 250h
0x18016700f  mov     rax, cs:__security_cookie
0x180167016  xor     rax, rsp
0x180167019  mov     [rbp+180h+var_40], rax
0x180167020  xor     r12d, r12d
0x180167023  mov     rdi, r8
0x180167026  mov     rbx, rdx
0x180167029  mov     r14, rcx
0x18016702c  test    rcx, rcx
0x18016702f  jnz     short loc_180167041
0x180167031  mov     rcx, [rdx]; lpString
0x180167034  lea     eax, [r14+1]
0x180167038  mov     [rcx], r12w
0x18016703c  jmp     loc_180167163
0x180167041  call    cs:__imp_lstrlenW
0x180167047  mov     rcx, r14
0x18016704a  lea     r15d, [rax+1]
0x18016704e  call    ?PathType@@YA?AW4iptEnum@@PEBG@Z; PathType(ushort const *)
0x180167053  cmp     eax, 3
0x180167056  jnz     short loc_18016707A
0x180167058  xor     r8d, r8d
0x18016705b  mov     edx, r15d
0x18016705e  mov     rcx, rbx
0x180167061  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x180167066  test    al, al
0x180167068  jz      loc_180167204
0x18016706e  mov     rcx, [rbx]
0x180167071  mov     [rcx], r12w
0x180167075  jmp     loc_18016714A
0x18016707a  lea     rax, [rsp+280h+Buffer]
0x18016707f  mov     r13d, 104h
0x180167085  mov     [rsp+280h+nBufferLength], r13d
0x18016708a  mov     [rsp+280h+lpBuffer], rax
0x18016708f  test    rdi, rdi
0x180167092  jz      short loc_1801670A7
0x180167094  cmp     [rdi], r12w
0x180167098  jz      short loc_1801670A7
0x18016709a  mov     rcx, rdi; lpString
0x18016709d  call    cs:__imp_lstrlenW
0x1801670a3  mov     esi, eax
0x1801670a5  jmp     short loc_1801670FA
0x1801670a7  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x1801670ac  mov     ecx, r13d; nBufferLength
0x1801670af  call    cs:__imp_GetCurrentDirectoryW
0x1801670b5  mov     esi, eax
0x1801670b7  test    eax, eax
0x1801670b9  jz      loc_1801671F2
0x1801670bf  cmp     eax, [rsp+280h+nBufferLength]
0x1801670c3  jbe     short loc_1801670F5
0x1801670c5  xor     r8d, r8d
0x1801670c8  lea     rcx, [rsp+280h+lpBuffer]
0x1801670cd  mov     edx, eax
0x1801670cf  call    ?SetSize@?$CAPITempBuffer@G$0BAE@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,260>::SetSize(int,bool)
0x1801670d4  test    al, al
0x1801670d6  jz      loc_1801671F2
0x1801670dc  mov     rdx, [rsp+280h+lpBuffer]; lpBuffer
0x1801670e1  mov     ecx, [rsp+280h+nBufferLength]; nBufferLength
0x1801670e5  call    cs:__imp_GetCurrentDirectoryW
0x1801670eb  mov     esi, eax
0x1801670ed  test    eax, eax
0x1801670ef  jz      loc_1801671F2
0x1801670f5  mov     rdi, [rsp+280h+lpBuffer]
0x1801670fa  cmp     word ptr [r14], 5Ch ; '\'
0x1801670ff  jnz     loc_18016718D
0x180167105  lea     edx, [r15+2]
0x180167109  xor     r8d, r8d
0x18016710c  mov     rcx, rbx
0x18016710f  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x180167114  test    al, al
0x180167116  jz      loc_1801671F2
0x18016711c  mov     rcx, [rbx]
0x18016711f  movzx   eax, word ptr [rdi]
0x180167122  mov     [rcx], ax
0x180167125  mov     rcx, [rbx]
0x180167128  movzx   eax, word ptr [rdi+2]
0x18016712c  mov     [rcx+2], ax
0x180167130  mov     rcx, [rbx]
0x180167133  mov     [rcx+4], r12w
0x180167138  cmp     [rsp+280h+nBufferLength], r13d
0x18016713d  jle     short loc_18016714A
0x18016713f  mov     rcx, [rsp+280h+lpBuffer]; hMem
0x180167144  call    cs:__imp_GlobalFree
0x18016714a  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x18016714e  mov     r8, r14; unsigned __int16 *
0x180167151  mov     rcx, [rbx]; unsigned __int16 *
0x180167154  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180167159  test    eax, eax
0x18016715b  mov     ecx, r12d
0x18016715e  setns   cl
0x180167161  mov     eax, ecx
0x180167163  mov     rcx, [rbp+180h+var_40]
0x18016716a  xor     rcx, rsp; StackCookie
0x18016716d  call    __security_check_cookie
0x180167172  mov     rbx, [rsp+280h+arg_18]
0x18016717a  add     rsp, 250h
0x180167181  pop     r15
0x180167183  pop     r14
0x180167185  pop     r13
0x180167187  pop     r12
0x180167189  pop     rdi
0x18016718a  pop     rsi
0x18016718b  pop     rbp
0x18016718c  retn
0x18016718d  mov     rcx, rdi; lpString
0x180167190  call    cs:__imp_lstrlenW
0x180167196  lea     edx, [r15+2]
0x18016719a  xor     r8d, r8d
0x18016719d  add     edx, eax
0x18016719f  mov     rcx, rbx
0x1801671a2  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x1801671a7  test    al, al
0x1801671a9  jz      short loc_1801671F2
0x1801671ab  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x1801671af  mov     r8, rdi; unsigned __int16 *
0x1801671b2  mov     rcx, [rbx]; unsigned __int16 *
0x1801671b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801671ba  test    eax, eax
0x1801671bc  js      short loc_1801671F2
0x1801671be  test    esi, esi
0x1801671c0  jz      loc_180167138
0x1801671c6  lea     eax, [rsi-1]
0x1801671c9  movsxd  rcx, eax
0x1801671cc  cmp     word ptr [rdi+rcx*2], 5Ch ; '\'
0x1801671d1  jz      loc_180167138
0x1801671d7  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x1801671db  lea     r8, asc_18026F7A4; "\\"
0x1801671e2  mov     rcx, [rbx]; unsigned __int16 *
0x1801671e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801671ea  test    eax, eax
0x1801671ec  jns     loc_180167138
0x1801671f2  cmp     [rsp+280h+nBufferLength], r13d
0x1801671f7  jle     short loc_180167204
0x1801671f9  mov     rcx, [rsp+280h+lpBuffer]; hMem
0x1801671fe  call    cs:__imp_GlobalFree
0x180167204  xor     eax, eax
0x180167206  jmp     loc_180167163
```
