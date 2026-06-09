# PerfDiagShared::GetDriverImageName(ushort *,unsigned __int64,ushort const * *,ushort const *)

- ea: `0x1800cea54`
- end: `0x1800ceb78`
- name: `?GetDriverImageName@PerfDiagShared@@YAJPEAG_KPEAPEBGPEBG@Z`
- size: `292`
- prototype: `__int64 __fastcall(PerfDiagShared *__hidden this, unsigned __int16 *, unsigned __int64, const unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800c3dc4`

## callees

- `0x18001a56c`
- `0x180041bb4`
- `0x180081d2c`
- `0x1800cea54`
- `0x1800cee94`

## import_xrefs

- `msvcrt!wcschr` at `0x1800ceaa3`
- `msvcrt!wcschr` at `0x1800ceaa3`
- `msvcrt!_wcsnicmp` at `0x1800cea89`
- `msvcrt!_wcsnicmp` at `0x1800cea89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceaff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceaff`

## string_xrefs

- `0x1800ceaea`: `ImagePath`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::GetDriverImageName(
        PerfDiagShared *this,
        unsigned __int16 *a2,
        __int64 a3,
        const wchar_t *a4)
{
  wchar_t *v4; // rbx
  const unsigned __int16 *v6; // r8
  int v7; // ebx
  signed int LastError; // eax
  int v10; // eax
  unsigned int v11; // ecx
  _QWORD v12[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+80h] [rbp+18h] BYREF

  v13 = a3;
  v4 = (wchar_t *)a4;
  if ( !a4 || !this )
    return 2147500035LL;
  if ( _wcsnicmp(a4, L"\\Driver\\", 8u) )
  {
    if ( wcschr(v4, 0x5Cu) )
    {
      if ( !*v4 || v4[1] != 58 || v4[2] != 92 )
        return 2147942487LL;
      v10 = StringCchCopyW((unsigned __int16 *)this, 0x100u, v4);
      v11 = 0;
      if ( v10 < 0 )
        return (unsigned int)v10;
      return v11;
    }
  }
  else
  {
    v4 += 8;
  }
  memset(v12, 0, 24);
  LODWORD(v13) = 256;
  v7 = PerfDiagShared::openServiceKey((PerfDiagShared *)v12, (struct ATL::CRegKey *)v4, v6);
  if ( v7 < 0 )
  {
LABEL_11:
    ATL::CRegKey::Close((ATL::CRegKey *)v12);
    return (unsigned int)v7;
  }
  if ( (unsigned int)ATL::CRegKey::QueryStringValue(
                       (ATL::CRegKey *)v12,
                       L"ImagePath",
                       (unsigned __int16 *)this,
                       (unsigned int *)&v13) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError;
    goto LABEL_11;
  }
  *((_WORD *)this + 255) = 0;
  ATL::CRegKey::Close((ATL::CRegKey *)v12);
  return 0;
}

```

## disassembly

```asm
0x1800cea54  mov     [rsp+arg_10], r8
0x1800cea59  push    rbx
0x1800cea5a  push    rbp
0x1800cea5b  push    rsi
0x1800cea5c  push    rdi
0x1800cea5d  sub     rsp, 48h
0x1800cea61  xor     esi, esi
0x1800cea63  mov     rbx, r9
0x1800cea66  mov     rdi, rcx
0x1800cea69  test    r9, r9
0x1800cea6c  jz      loc_1800CEB6A
0x1800cea72  test    rcx, rcx
0x1800cea75  jz      loc_1800CEB6A
0x1800cea7b  lea     r8d, [rsi+8]; MaxCount
0x1800cea7f  mov     rcx, rbx; String1
0x1800cea82  lea     rdx, aDriver; "\\Driver\\"
0x1800cea89  call    cs:__imp__wcsnicmp
0x1800cea8f  test    eax, eax
0x1800cea91  jnz     short loc_1800CEA99
0x1800cea93  add     rbx, 10h
0x1800cea97  jmp     short loc_1800CEAB2
0x1800cea99  mov     ebp, 5Ch ; '\'
0x1800cea9e  mov     rcx, rbx; Str
0x1800ceaa1  mov     edx, ebp; Ch
0x1800ceaa3  call    cs:__imp_wcschr
0x1800ceaa9  test    rax, rax
0x1800ceaac  jnz     loc_1800CEB36
0x1800ceab2  mov     rdx, rbx; struct ATL::CRegKey *
0x1800ceab5  mov     [rsp+68h+var_48], rsi
0x1800ceaba  lea     rcx, [rsp+68h+var_48]; this
0x1800ceabf  mov     [rsp+68h+var_40], rsi
0x1800ceac4  mov     [rsp+68h+var_38], rsi
0x1800ceac9  mov     dword ptr [rsp+68h+arg_10], 100h
0x1800cead4  call    ?openServiceKey@PerfDiagShared@@YAJAEAVCRegKey@ATL@@PEBG@Z; PerfDiagShared::openServiceKey(ATL::CRegKey &,ushort const *)
0x1800cead9  mov     ebx, eax
0x1800ceadb  test    eax, eax
0x1800ceadd  js      short loc_1800CEB13
0x1800ceadf  lea     r9, [rsp+68h+arg_10]; unsigned int *
0x1800ceae7  mov     r8, rdi; unsigned __int16 *
0x1800ceaea  lea     rdx, aImagepath; "ImagePath"
0x1800ceaf1  lea     rcx, [rsp+68h+var_48]; this
0x1800ceaf6  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800ceafb  test    eax, eax
0x1800ceafd  jz      short loc_1800CEB21
0x1800ceaff  call    cs:__imp_GetLastError
0x1800ceb05  test    eax, eax
0x1800ceb07  jle     short loc_1800CEB11
0x1800ceb09  movzx   eax, ax
0x1800ceb0c  or      eax, 80070000h
0x1800ceb11  mov     ebx, eax
0x1800ceb13  lea     rcx, [rsp+68h+var_48]; this
0x1800ceb18  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800ceb1d  mov     eax, ebx
0x1800ceb1f  jmp     short loc_1800CEB6F
0x1800ceb21  lea     rcx, [rsp+68h+var_48]; this
0x1800ceb26  mov     [rdi+1FEh], si
0x1800ceb2d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800ceb32  xor     eax, eax
0x1800ceb34  jmp     short loc_1800CEB6F
0x1800ceb36  cmp     [rbx], si
0x1800ceb39  jz      short loc_1800CEB63
0x1800ceb3b  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800ceb40  jnz     short loc_1800CEB63
0x1800ceb42  cmp     [rbx+4], bp
0x1800ceb46  jnz     short loc_1800CEB63
0x1800ceb48  mov     r8, rbx; unsigned __int16 *
0x1800ceb4b  mov     edx, 100h; unsigned __int64
0x1800ceb50  mov     rcx, rdi; unsigned __int16 *
0x1800ceb53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ceb58  test    eax, eax
0x1800ceb5a  mov     ecx, esi
0x1800ceb5c  cmovs   ecx, eax
0x1800ceb5f  mov     eax, ecx
0x1800ceb61  jmp     short loc_1800CEB6F
0x1800ceb63  mov     eax, 80070057h
0x1800ceb68  jmp     short loc_1800CEB6F
0x1800ceb6a  mov     eax, 80004003h
0x1800ceb6f  add     rsp, 48h
0x1800ceb73  pop     rdi
0x1800ceb74  pop     rsi
0x1800ceb75  pop     rbp
0x1800ceb76  pop     rbx
0x1800ceb77  retn
```
