# IpToSockAddr(char *,STBUFF *)

- ea: `0x180001af4`
- end: `0x180001c6b`
- name: `?IpToSockAddr@@YAJPEADPEAVSTBUFF@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(char *, struct STBUFF *this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002dd0`
- `0x180004f8c`
- `0x180005ab8`

## callees

- `0x180001948`
- `0x180001a2c`
- `0x180001af4`
- `0x180001fa4`
- `0x1800067c0`

## import_xrefs

- `msvcrt!strpbrk` at `0x180001b3e`
- `msvcrt!strpbrk` at `0x180001b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c3f`
- `WS2_32!WSAStringToAddressA` at `0x180001bbe`
- `WS2_32!WSAStringToAddressA` at `0x180001bbe`
- `WS2_32!__imp_WSAGetLastError` at `0x180001bc9`
- `WS2_32!__imp_WSAGetLastError` at `0x180001bc9`

## pseudocode

```c
__int64 __fastcall IpToSockAddr(char *a1, struct STBUFF *this)
{
  int appended; // ebx
  char *v5; // rax
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r14
  INT v9; // edx
  struct sockaddr *v10; // r9
  int Error; // eax
  int AddressLength[4]; // [rsp+30h] [rbp-39h] BYREF
  void **v14; // [rsp+40h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-21h]
  unsigned int v16; // [rsp+50h] [rbp-19h]
  char v17; // [rsp+5Ch] [rbp-Dh] BYREF

  STBUFF::STBUFF((STBUFF *)&v14, (int)this);
  AddressLength[0] = 0;
  appended = 0;
  v5 = strpbrk(a1, "/");
  if ( v5 )
  {
    v6 = (_DWORD)v5 - (_DWORD)a1;
    if ( v6 == -1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a1[v7] );
    }
    else
    {
      LODWORD(v7) = v6;
    }
    appended = STBUFF::AppendData((STBUFF *)&v14, a1, v7, 0);
    if ( appended < 0 )
      goto LABEL_23;
    *((_BYTE *)hMem + v16) = 0;
    *((_BYTE *)hMem + v16 + 1) = 0;
    a1 = (char *)hMem;
  }
  v8 = 0;
  while ( 1 )
  {
    v9 = *((_DWORD *)&qword_180008890 + v8);
    v10 = (struct sockaddr *)*((_QWORD *)this + 1);
    AddressLength[0] = *((_DWORD *)this + 5);
    if ( WSAStringToAddressA(a1, v9, 0, v10, AddressLength) != -1 )
      break;
    Error = WSAGetLastError();
    if ( Error == 10014 )
    {
      if ( AddressLength[0] < 0 || AddressLength[0] <= *((_DWORD *)this + 5) )
      {
        appended = 10014;
        goto LABEL_23;
      }
      appended = STBUFF::Resize(this, AddressLength[0]);
      if ( appended < 0 )
        goto LABEL_23;
    }
    else if ( Error == 10093 || Error == 8 || (v8 = (unsigned int)(v8 + 1), (unsigned int)v8 >= 2) )
    {
      appended = Error;
      goto LABEL_23;
    }
  }
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL) = 0;
  if ( AddressLength[0] <= *((_DWORD *)this + 5) )
    *((_DWORD *)this + 4) = AddressLength[0];
LABEL_23:
  v14 = &STBUFF::`vftable';
  if ( hMem != &v17 )
    LocalFree(hMem);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180001af4  mov     [rsp-8+arg_10], rbx
0x180001af9  mov     [rsp-8+arg_18], rsi
0x180001afe  push    rbp
0x180001aff  push    rdi
0x180001b00  push    r14
0x180001b02  lea     rbp, [rsp-47h]
0x180001b07  sub     rsp, 0B0h
0x180001b0e  mov     rax, cs:__security_cookie
0x180001b15  xor     rax, rsp
0x180001b18  mov     [rbp+57h+var_20], rax
0x180001b1c  mov     rsi, rcx
0x180001b1f  mov     rdi, rdx
0x180001b22  lea     rcx, [rbp+57h+var_80]; this
0x180001b26  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180001b2b  lea     rdx, Control; "/"
0x180001b32  mov     [rbp+57h+AddressLength], 0
0x180001b39  mov     rcx, rsi; Str
0x180001b3c  xor     ebx, ebx
0x180001b3e  call    cs:__imp_strpbrk
0x180001b44  test    rax, rax
0x180001b47  jz      short loc_180001B97
0x180001b49  sub     eax, esi
0x180001b4b  cmp     eax, 0FFFFFFFFh
0x180001b4e  jnz     short loc_180001B5F
0x180001b50  or      r8, 0FFFFFFFFFFFFFFFFh
0x180001b54  inc     r8
0x180001b57  cmp     [rsi+r8], bl
0x180001b5b  jnz     short loc_180001B54
0x180001b5d  jmp     short loc_180001B62
0x180001b5f  mov     r8d, eax; unsigned int
0x180001b62  xor     r9d, r9d; unsigned int
0x180001b65  lea     rcx, [rbp+57h+var_80]; this
0x180001b69  mov     rdx, rsi; void *
0x180001b6c  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180001b71  mov     ebx, eax
0x180001b73  test    eax, eax
0x180001b75  js      loc_180001C27
0x180001b7b  mov     edx, [rbp+57h+var_70]
0x180001b7e  mov     rcx, [rbp+57h+hMem]
0x180001b82  mov     byte ptr [rdx+rcx], 0
0x180001b86  mov     edx, [rbp+57h+var_70]
0x180001b89  mov     rcx, [rbp+57h+hMem]
0x180001b8d  inc     edx
0x180001b8f  mov     byte ptr [rdx+rcx], 0
0x180001b93  mov     rsi, [rbp+57h+hMem]
0x180001b97  xor     r14d, r14d
0x180001b9a  mov     eax, [rdi+14h]
0x180001b9d  lea     rcx, qword_180008890
0x180001ba4  mov     edx, [rcx+r14*4]; AddressFamily
0x180001ba8  xor     r8d, r8d; lpProtocolInfo
0x180001bab  mov     r9, [rdi+8]; lpAddress
0x180001baf  mov     rcx, rsi; AddressString
0x180001bb2  mov     [rbp+57h+AddressLength], eax
0x180001bb5  lea     rax, [rbp+57h+AddressLength]
0x180001bb9  mov     [rsp+0C0h+lpAddressLength], rax; lpAddressLength
0x180001bbe  call    cs:__imp_WSAStringToAddressA
0x180001bc4  cmp     eax, 0FFFFFFFFh
0x180001bc7  jnz     short loc_180001C12
0x180001bc9  call    cs:__imp_WSAGetLastError
0x180001bcf  cmp     eax, 271Eh
0x180001bd4  jnz     short loc_180001BF2
0x180001bd6  mov     edx, [rbp+57h+AddressLength]; unsigned int
0x180001bd9  test    edx, edx
0x180001bdb  js      short loc_180001C0B
0x180001bdd  cmp     edx, [rdi+14h]
0x180001be0  jbe     short loc_180001C0B
0x180001be2  mov     rcx, rdi; this
0x180001be5  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x180001bea  mov     ebx, eax
0x180001bec  test    eax, eax
0x180001bee  jns     short loc_180001B9A
0x180001bf0  jmp     short loc_180001C27
0x180001bf2  cmp     eax, 276Dh
0x180001bf7  jz      short loc_180001C07
0x180001bf9  cmp     eax, 8
0x180001bfc  jz      short loc_180001C07
0x180001bfe  inc     r14d
0x180001c01  cmp     r14d, 2
0x180001c05  jb      short loc_180001B9A
0x180001c07  mov     ebx, eax
0x180001c09  jmp     short loc_180001C27
0x180001c0b  mov     ebx, 271Eh
0x180001c10  jmp     short loc_180001C27
0x180001c12  mov     rcx, [rdi+8]
0x180001c16  xor     eax, eax
0x180001c18  mov     [rcx+2], ax
0x180001c1c  mov     eax, [rbp+57h+AddressLength]
0x180001c1f  cmp     eax, [rdi+14h]
0x180001c22  ja      short loc_180001C27
0x180001c24  mov     [rdi+10h], eax
0x180001c27  mov     rcx, [rbp+57h+hMem]; hMem
0x180001c2b  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180001c32  mov     [rbp+57h+var_80], rax
0x180001c36  lea     rax, [rbp+57h+var_64]
0x180001c3a  cmp     rcx, rax
0x180001c3d  jz      short loc_180001C45
0x180001c3f  call    cs:__imp_LocalFree
0x180001c45  mov     eax, ebx
0x180001c47  mov     rcx, [rbp+57h+var_20]
0x180001c4b  xor     rcx, rsp; StackCookie
0x180001c4e  call    __security_check_cookie
0x180001c53  lea     r11, [rsp+0C0h+var_10]
0x180001c5b  mov     rbx, [r11+30h]
0x180001c5f  mov     rsi, [r11+38h]
0x180001c63  mov     rsp, r11
0x180001c66  pop     r14
0x180001c68  pop     rdi
0x180001c69  pop     rbp
0x180001c6a  retn
```
