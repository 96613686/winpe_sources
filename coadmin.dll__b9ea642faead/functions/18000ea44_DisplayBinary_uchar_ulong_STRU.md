# DisplayBinary(uchar *,ulong,STRU *)

- ea: `0x18000ea44`
- end: `0x18000eb47`
- name: `?DisplayBinary@@YAJPEAEKPEAVSTRU@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ec98`

## callees

- `0x18000ea44`
- `0x18000fb50`

## import_xrefs

- `msvcrt!_ultow` at `0x18000eabf`
- `msvcrt!_ultow` at `0x18000eabf`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000ead7`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eae9`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eb04`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eb17`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000ead7`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eae9`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eb04`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eb17`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000eaa7`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000eaa7`
- `IisRTL!?Resize@STRU@@QEAAJK@Z` at `0x18000ea83`
- `IisRTL!?Resize@STRU@@QEAAJK@Z` at `0x18000ea83`

## pseudocode

```c
int __fastcall DisplayBinary(unsigned __int8 *a1, unsigned int a2, struct STRU *a3)
{
  int result; // eax
  unsigned int v7; // ebx
  wchar_t Buffer[2]; // [rsp+20h] [rbp-38h] BYREF
  __int16 v9; // [rsp+24h] [rbp-34h]

  *(_DWORD *)Buffer = 0;
  v9 = 0;
  if ( (int)STRU::Resize(a3, 2 * ((a2 >> 4) + 3 * (a2 + 1))) < 0 )
    return -2147024882;
  v7 = 0;
  STRU::Copy(a3, L"\r\n");
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    _ultow(*a1, Buffer, 16);
    if ( !Buffer[1] )
    {
      result = STRU::Append(a3, L"0");
      if ( result < 0 )
        break;
    }
    result = STRU::Append(a3, Buffer);
    if ( result < 0 )
      break;
    if ( (++v7 & 0xF) != 0 )
    {
      if ( (int)STRU::Append(a3, L" ") < 0 )
        return -2147024882;
    }
    else
    {
      result = STRU::Append(a3, L"\r\n");
      if ( result < 0 )
        return result;
    }
    ++a1;
    if ( v7 >= a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ea44  push    rbx
0x18000ea46  push    rbp
0x18000ea47  push    rsi
0x18000ea48  push    rdi
0x18000ea49  push    r14
0x18000ea4b  sub     rsp, 30h
0x18000ea4f  mov     rax, cs:__security_cookie
0x18000ea56  xor     rax, rsp
0x18000ea59  mov     [rsp+58h+var_30], rax
0x18000ea5e  xor     eax, eax
0x18000ea60  mov     ebp, edx
0x18000ea62  mov     dword ptr [rsp+58h+Buffer], eax
0x18000ea66  mov     rsi, rcx
0x18000ea69  mov     [rsp+58h+var_34], ax
0x18000ea6e  mov     rcx, r8
0x18000ea71  lea     eax, [rdx+1]
0x18000ea74  mov     rdi, r8
0x18000ea77  lea     edx, [rax+rax*2]
0x18000ea7a  mov     eax, ebp
0x18000ea7c  shr     eax, 4
0x18000ea7f  add     edx, eax
0x18000ea81  add     edx, edx
0x18000ea83  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000ea89  xor     r14d, r14d
0x18000ea8c  test    eax, eax
0x18000ea8e  jns     short loc_18000EA9A
0x18000ea90  mov     eax, 8007000Eh
0x18000ea95  jmp     loc_18000EB2F
0x18000ea9a  lea     rdx, asc_180013198; "\r\n"
0x18000eaa1  mov     rcx, rdi
0x18000eaa4  mov     ebx, r14d
0x18000eaa7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000eaad  test    ebp, ebp
0x18000eaaf  jz      short loc_18000EB2C
0x18000eab1  movzx   ecx, byte ptr [rsi]; Value
0x18000eab4  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18000eab9  mov     r8d, 10h; Radix
0x18000eabf  call    cs:__imp__ultow
0x18000eac5  cmp     [rsp+58h+Buffer+2], r14w
0x18000eacb  jnz     short loc_18000EAE1
0x18000eacd  lea     rdx, a0; "0"
0x18000ead4  mov     rcx, rdi
0x18000ead7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000eadd  test    eax, eax
0x18000eadf  js      short loc_18000EB2F
0x18000eae1  lea     rdx, [rsp+58h+Buffer]
0x18000eae6  mov     rcx, rdi
0x18000eae9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000eaef  test    eax, eax
0x18000eaf1  js      short loc_18000EB2F
0x18000eaf3  inc     ebx
0x18000eaf5  mov     rcx, rdi
0x18000eaf8  test    bl, 0Fh
0x18000eafb  jnz     short loc_18000EB10
0x18000eafd  lea     rdx, asc_180013198; "\r\n"
0x18000eb04  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000eb0a  test    eax, eax
0x18000eb0c  js      short loc_18000EB2F
0x18000eb0e  jmp     short loc_18000EB25
0x18000eb10  lea     rdx, asc_180013088; " "
0x18000eb17  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000eb1d  test    eax, eax
0x18000eb1f  js      loc_18000EA90
0x18000eb25  inc     rsi
0x18000eb28  cmp     ebx, ebp
0x18000eb2a  jb      short loc_18000EAB1
0x18000eb2c  mov     eax, r14d
0x18000eb2f  mov     rcx, [rsp+58h+var_30]
0x18000eb34  xor     rcx, rsp; StackCookie
0x18000eb37  call    __security_check_cookie
0x18000eb3c  add     rsp, 30h
0x18000eb40  pop     r14
0x18000eb42  pop     rdi
0x18000eb43  pop     rsi
0x18000eb44  pop     rbp
0x18000eb45  pop     rbx
0x18000eb46  retn
```
