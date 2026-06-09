# GetComputerInfo(int,ushort *)

- ea: `0x180002bc0`
- end: `0x180002dbc`
- name: `?GetComputerInfo@@YAJHPEAG@Z`
- size: `508`
- prototype: `__int64 __fastcall(_NETSETUP_JOIN_STATUS, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800022b4`

## callees

- `0x180001014`
- `0x180001020`
- `0x180002bc0`
- `0x180004348`
- `0x18000440c`
- `0x180004770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d7f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180002c6d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180002c6d`
- `wkscli!NetGetJoinInformation` at `0x180002c88`
- `wkscli!NetGetJoinInformation` at `0x180002c88`
- `netutils!NetApiBufferFree` at `0x180002ce8`
- `netutils!NetApiBufferFree` at `0x180002ce8`

## pseudocode

```c
__int64 __fastcall GetComputerInfo(_NETSETUP_JOIN_STATUS a1, unsigned __int16 *a2)
{
  WCHAR *v4; // rbp
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rax
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // rcx
  signed int LastError; // eax
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+50h] [rbp+8h] BYREF
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF
  LPWSTR NameBuffer; // [rsp+60h] [rbp+18h] BYREF

  BufferType = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  if ( !a2 )
    return 2147942487LL;
  nSize = 16;
  BufferType = NetSetupUnknownStatus;
  NameBuffer = 0;
  v4 = (WCHAR *)operator new[](0x20u);
  if ( v4 )
  {
    v5 = (unsigned __int16 *)operator new[](0x800u);
    if ( v5 )
    {
      if ( GetComputerNameW(v4, &nSize) )
      {
        if ( NetGetJoinInformation(v4, &NameBuffer, &BufferType) )
        {
          StringCchPrintfW(v5, 0x400u, L"NotJoined");
        }
        else
        {
          switch ( BufferType )
          {
            case NetSetupDomainName:
              StringCchPrintfW(v5, 0x400u, L"Domain:%s", NameBuffer);
              break;
            case NetSetupWorkgroupName:
              StringCchPrintfW(v5, 0x400u, L"Workgroup:%s", NameBuffer);
              break;
            case NetSetupUnjoined:
              StringCchPrintfW(v5, 0x400u, L"NotJoined");
              break;
          }
          if ( NameBuffer )
            NetApiBufferFree(NameBuffer);
        }
        v7 = 2147483646;
        v8 = v4;
        v9 = 1024;
        v10 = a2;
        do
        {
          if ( !v7 )
            break;
          if ( !*v8 )
            break;
          *v10++ = *v8++;
          --v7;
          --v9;
        }
        while ( v9 );
        v11 = v10 - 1;
        v6 = v9 == 0 ? 0x8007007A : 0;
        if ( v9 )
          v11 = v10;
        *v11 = 0;
        if ( v9 )
        {
          v6 = StringCchCatW(a2, 0x400u, L"/");
          if ( !v6 )
            v6 = StringCchCatW(a2, 0x400u, v5);
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_34;
    }
  }
  else
  {
    v5 = 0;
  }
  v6 = -2147024882;
  if ( v4 )
LABEL_34:
    operator delete[](v4);
  if ( v5 )
    operator delete[](v5);
  return v6;
}

```

## disassembly

```asm
0x180002bc0  mov     [rsp+arg_18], rbx
0x180002bc5  mov     [rsp+BufferType], ecx
0x180002bc9  push    rbp
0x180002bca  push    rsi
0x180002bcb  push    rdi
0x180002bcc  push    r14
0x180002bce  push    r15
0x180002bd0  sub     rsp, 20h
0x180002bd4  mov     r14, rdx
0x180002bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bde  lea     rax, WPP_GLOBAL_Control
0x180002be5  cmp     rcx, rax
0x180002be8  jz      short loc_180002C05
0x180002bea  cmp     byte ptr [rcx+19h], 4
0x180002bee  jb      short loc_180002C05
0x180002bf0  mov     rcx, [rcx+10h]
0x180002bf4  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002bfb  mov     edx, 0Dh
0x180002c00  call    WPP_SF_s
0x180002c05  xor     r15d, r15d
0x180002c08  test    r14, r14
0x180002c0b  jnz     short loc_180002C17
0x180002c0d  mov     eax, 80070057h
0x180002c12  jmp     loc_180002DAB
0x180002c17  mov     ecx, 20h ; ' '; unsigned __int64
0x180002c1c  mov     [rsp+48h+nSize], 10h
0x180002c24  mov     [rsp+48h+BufferType], r15d
0x180002c29  mov     [rsp+48h+NameBuffer], r15
0x180002c2e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002c33  mov     rbp, rax
0x180002c36  test    rax, rax
0x180002c39  jnz     short loc_180002C40
0x180002c3b  mov     rdi, r15
0x180002c3e  jmp     short loc_180002C52
0x180002c40  mov     ecx, 800h; unsigned __int64
0x180002c45  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002c4a  mov     rdi, rax
0x180002c4d  test    rax, rax
0x180002c50  jnz     short loc_180002C65
0x180002c52  mov     ebx, 8007000Eh
0x180002c57  test    rbp, rbp
0x180002c5a  jz      loc_180002D9C
0x180002c60  jmp     loc_180002D94
0x180002c65  lea     rdx, [rsp+48h+nSize]; nSize
0x180002c6a  mov     rcx, rbp; lpBuffer
0x180002c6d  call    cs:__imp_GetComputerNameW
0x180002c73  test    eax, eax
0x180002c75  jz      loc_180002D7F
0x180002c7b  lea     r8, [rsp+48h+BufferType]; BufferType
0x180002c80  mov     rcx, rbp; lpServer
0x180002c83  lea     rdx, [rsp+48h+NameBuffer]; lpNameBuffer
0x180002c88  call    cs:__imp_NetGetJoinInformation
0x180002c8e  mov     esi, 400h
0x180002c93  test    eax, eax
0x180002c95  jnz     short loc_180002CF0
0x180002c97  mov     eax, [rsp+48h+BufferType]
0x180002c9b  cmp     eax, 3
0x180002c9e  jnz     short loc_180002CA9
0x180002ca0  lea     r8, aDomainS; "Domain:%s"
0x180002ca7  jmp     short loc_180002CB5
0x180002ca9  cmp     eax, 2
0x180002cac  jnz     short loc_180002CC7
0x180002cae  lea     r8, aWorkgroupS; "Workgroup:%s"
0x180002cb5  mov     r9, [rsp+48h+NameBuffer]
0x180002cba  mov     rdx, rsi; unsigned __int64
0x180002cbd  mov     rcx, rdi; unsigned __int16 *
0x180002cc0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002cc5  jmp     short loc_180002CDE
0x180002cc7  cmp     eax, 1
0x180002cca  jnz     short loc_180002CDE
0x180002ccc  lea     r8, aNotjoined; "NotJoined"
0x180002cd3  mov     rdx, rsi; unsigned __int64
0x180002cd6  mov     rcx, rdi; unsigned __int16 *
0x180002cd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002cde  mov     rcx, [rsp+48h+NameBuffer]; Buffer
0x180002ce3  test    rcx, rcx
0x180002ce6  jz      short loc_180002D02
0x180002ce8  call    cs:__imp_NetApiBufferFree
0x180002cee  jmp     short loc_180002D02
0x180002cf0  lea     r8, aNotjoined; "NotJoined"
0x180002cf7  mov     rdx, rsi; unsigned __int64
0x180002cfa  mov     rcx, rdi; unsigned __int16 *
0x180002cfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002d02  mov     eax, 7FFFFFFEh
0x180002d07  mov     rcx, rbp
0x180002d0a  mov     rdx, rsi
0x180002d0d  mov     r8, r14
0x180002d10  test    rax, rax
0x180002d13  jz      short loc_180002D34
0x180002d15  movzx   r9d, word ptr [rcx]
0x180002d19  test    r9w, r9w
0x180002d1d  jz      short loc_180002D34
0x180002d1f  mov     [r8], r9w
0x180002d23  add     rcx, 2
0x180002d27  add     r8, 2
0x180002d2b  dec     rax
0x180002d2e  sub     rdx, 1
0x180002d32  jnz     short loc_180002D10
0x180002d34  mov     rax, rdx
0x180002d37  lea     rcx, [r8-2]
0x180002d3b  neg     rax
0x180002d3e  sbb     ebx, ebx
0x180002d40  not     ebx
0x180002d42  and     ebx, 8007007Ah
0x180002d48  test    rdx, rdx
0x180002d4b  cmovnz  rcx, r8
0x180002d4f  mov     [rcx], r15w
0x180002d53  jz      short loc_180002D94
0x180002d55  lea     r8, asc_1800075AC; "/"
0x180002d5c  mov     rdx, rsi; unsigned __int64
0x180002d5f  mov     rcx, r14; unsigned __int16 *
0x180002d62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002d67  mov     ebx, eax
0x180002d69  test    eax, eax
0x180002d6b  jnz     short loc_180002D94
0x180002d6d  mov     r8, rdi; unsigned __int16 *
0x180002d70  mov     rdx, rsi; unsigned __int64
0x180002d73  mov     rcx, r14; unsigned __int16 *
0x180002d76  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002d7b  mov     ebx, eax
0x180002d7d  jmp     short loc_180002D94
0x180002d7f  call    cs:__imp_GetLastError
0x180002d85  mov     ebx, eax
0x180002d87  test    eax, eax
0x180002d89  jle     short loc_180002D94
0x180002d8b  movzx   ebx, ax
0x180002d8e  or      ebx, 80070000h
0x180002d94  mov     rcx, rbp; Block
0x180002d97  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002d9c  test    rdi, rdi
0x180002d9f  jz      short loc_180002DA9
0x180002da1  mov     rcx, rdi; Block
0x180002da4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002da9  mov     eax, ebx
0x180002dab  mov     rbx, [rsp+48h+arg_18]
0x180002db0  add     rsp, 20h
0x180002db4  pop     r15
0x180002db6  pop     r14
0x180002db8  pop     rdi
0x180002db9  pop     rsi
0x180002dba  pop     rbp
0x180002dbb  retn
```
