# IsWin32DeviceNamespacePathWithoutDriveLetter(ushort const *)

- ea: `0x18000bbc0`
- end: `0x18000bc75`
- name: `?IsWin32DeviceNamespacePathWithoutDriveLetter@@YA_NPEBG@Z`
- size: `181`
- prototype: `bool __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x18000bbc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bc27`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bc27`

## pseudocode

```c
bool __fastcall IsWin32DeviceNamespacePathWithoutDriveLetter(LPCWCH lpString1)
{
  unsigned __int64 v1; // rdi
  LPCWCH *i; // rsi
  WCHAR v4; // cx
  bool result; // al
  _QWORD v6[3]; // [rsp+30h] [rbp-48h] BYREF
  char v7; // [rsp+48h] [rbp-30h] BYREF

  v1 = -1;
  v6[0] = L"\\\\?\\";
  v6[1] = L"\\\\.\\";
  v6[2] = L"\\??\\";
  do
    ++v1;
  while ( lpString1[v1] );
  if ( v1 >= 4 )
  {
    for ( i = (LPCWCH *)v6; i != (LPCWCH *)&v7; ++i )
    {
      if ( CompareStringOrdinal(lpString1, 4, *i, 4, 0) == 2 )
      {
        result = v1 < 7
              || (v4 = lpString1[4], (unsigned __int16)(v4 - 65) > 0x19u) && (unsigned __int16)(v4 - 97) > 0x19u
              || lpString1[5] != 58
              || lpString1[6] != 92;
        return result;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bbc0  push    rbx
0x18000bbc2  push    rbp
0x18000bbc3  push    rsi
0x18000bbc4  push    rdi
0x18000bbc5  sub     rsp, 58h
0x18000bbc9  lea     rax, asc_18001A3E0; "\\\\?\\"
0x18000bbd0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000bbd4  mov     [rsp+78h+var_48], rax
0x18000bbd9  mov     rbx, rcx
0x18000bbdc  lea     rax, asc_18001A3F0; "\\\\.\\"
0x18000bbe3  xor     ebp, ebp
0x18000bbe5  mov     [rsp+78h+var_40], rax
0x18000bbea  lea     rax, asc_18001A400; "\\??\\"
0x18000bbf1  mov     [rsp+78h+var_38], rax
0x18000bbf6  inc     rdi
0x18000bbf9  cmp     [rcx+rdi*2], bp
0x18000bbfd  jnz     short loc_18000BBF6
0x18000bbff  cmp     rdi, 4
0x18000bc03  jb      short loc_18000BC6A
0x18000bc05  lea     rsi, [rsp+78h+var_48]
0x18000bc0a  lea     rax, [rsp+78h+var_30]
0x18000bc0f  cmp     rsi, rax
0x18000bc12  jz      short loc_18000BC6A
0x18000bc14  mov     r8, [rsi]; lpString2
0x18000bc17  mov     r9d, 4; cchCount2
0x18000bc1d  mov     edx, r9d; cchCount1
0x18000bc20  mov     [rsp+78h+bIgnoreCase], ebp; bIgnoreCase
0x18000bc24  mov     rcx, rbx; lpString1
0x18000bc27  call    cs:__imp_CompareStringOrdinal
0x18000bc2d  cmp     eax, 2
0x18000bc30  jz      short loc_18000BC38
0x18000bc32  add     rsi, 8
0x18000bc36  jmp     short loc_18000BC0A
0x18000bc38  cmp     rdi, 7
0x18000bc3c  jb      short loc_18000BC66
0x18000bc3e  movzx   ecx, word ptr [rbx+8]
0x18000bc42  lea     eax, [rcx-41h]
0x18000bc45  cmp     ax, 19h
0x18000bc49  jbe     short loc_18000BC55
0x18000bc4b  sub     cx, 61h ; 'a'
0x18000bc4f  cmp     cx, 19h
0x18000bc53  ja      short loc_18000BC66
0x18000bc55  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x18000bc5a  jnz     short loc_18000BC66
0x18000bc5c  cmp     word ptr [rbx+0Ch], 5Ch ; '\'
0x18000bc61  setnz   al
0x18000bc64  jmp     short loc_18000BC6C
0x18000bc66  mov     al, 1
0x18000bc68  jmp     short loc_18000BC6C
0x18000bc6a  xor     al, al
0x18000bc6c  add     rsp, 58h
0x18000bc70  pop     rdi
0x18000bc71  pop     rsi
0x18000bc72  pop     rbp
0x18000bc73  pop     rbx
0x18000bc74  retn
```
