# sub_1400B4ACA

- ea: `0x1400b4aca`
- end: `0x1400b4c1f`
- name: `sub_1400B4ACA`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b4aa0`
- `0x14037373d`

## callees

- `0x140086090`
- `0x1400b4aca`
- `0x1400b4c1f`
- `0x14010bdc0`
- `0x14010bdf0`
- `0x14011fa70`
- `0x140373764`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401b7f1e`
- `KERNEL32!GetLastError` at `0x1401b7f38`
- `KERNEL32!GetLastError` at `0x1401b7f1e`
- `KERNEL32!GetLastError` at `0x1401b7f38`
- `KERNEL32!HeapSetInformation` at `0x1401b7f52`
- `KERNEL32!HeapSetInformation` at `0x1401b7f52`
- `KERNEL32!SetDefaultDllDirectories` at `0x1401b7f08`
- `KERNEL32!SetDefaultDllDirectories` at `0x1401b7f2e`
- `KERNEL32!SetDefaultDllDirectories` at `0x1401b7f08`
- `KERNEL32!SetDefaultDllDirectories` at `0x1401b7f2e`

## pseudocode

```c
__int64 __fastcall sub_1400B4ACA(__int64 a1, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // rdi
  unsigned int v4; // esi
  __int64 v5; // r15
  unsigned int v7; // ecx
  __int64 v8; // [rsp+0h] [rbp-68h] BYREF
  __int128 v9; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h]

  LODWORD(v5) = a1 | a2;
  LOBYTE(v4) = 1;
  if ( (a1 | a2) != a1 )
  {
    v3 = a2;
    v2 = sub_140086090(a1);
    if ( (v3 & 0x200) != 0 )
      goto LABEL_32;
    goto LABEL_3;
  }
  while ( _security_cookie != ((unsigned __int64)&v8 ^ v10) )
  {
LABEL_32:
    if ( !SetDefaultDllDirectories(0xC00u)
      && (GetLastError() != 87 || !SetDefaultDllDirectories(0x800u))
      && GetLastError() != 5 )
    {
      goto LABEL_42;
    }
    BYTE1(qword_14043B818) |= 2u;
LABEL_3:
    if ( (v3 & 0x20) != 0 )
    {
      if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
        goto LABEL_42;
      LOBYTE(qword_14043B818) = qword_14043B818 | 0x20;
    }
    if ( (v3 & 0x400) != 0 )
    {
      v9 = 0;
      sub_14010BDF0(&v9, 0, 655360);
      if ( BYTE8(v9) != 1 )
        goto LABEL_42;
      if ( !(unsigned int)sub_1400B4C1F(&v9) )
      {
        BYTE1(qword_14043B818) |= 4u;
        if ( BYTE8(v9) == 1 )
          sub_14010BDC0(&v9);
        goto LABEL_9;
      }
      if ( BYTE8(v9) == 1 )
        sub_14010BDC0(&v9);
LABEL_42:
      v4 = 0;
    }
    else
    {
LABEL_9:
      if ( (v3 & 8) != 0 )
      {
        LODWORD(v9) = (((unsigned int)v5 >> 1) & 8 | ((unsigned int)v5 >> 6) & 1) + (((unsigned int)v5 >> 5) & 4) + 2;
        sub_140373764(1);
        qword_14043B818 = (unsigned __int8)v5 & 0xD8 | (unsigned __int64)qword_14043B818;
      }
      if ( (v3 & 0x100) != 0 )
      {
        LODWORD(v9) = 3;
        sub_140373764(3);
        BYTE1(qword_14043B818) |= 1u;
      }
      if ( (v3 & 0x800) != 0 )
      {
        LODWORD(v9) = 1;
        sub_140373764(4);
        BYTE1(qword_14043B818) |= 8u;
      }
      if ( (v3 & 0x1000) != 0 )
      {
        LODWORD(v9) = 1;
        sub_140373764(6);
        BYTE1(qword_14043B818) |= 0x10u;
      }
      if ( (v3 & 0x2000) != 0 )
      {
        LODWORD(v9) = 1;
        sub_140373764(2);
        BYTE1(qword_14043B818) |= 0x20u;
      }
      if ( (v3 & 0x10000) != 0 )
      {
        LODWORD(v9) = 1;
        sub_140373764(9);
        BYTE2(qword_14043B818) |= 1u;
      }
      if ( v2 >= 8 )
      {
        if ( (v3 & 0x20000) != 0 )
        {
          LODWORD(v9) = 1;
          sub_140373764(8);
          BYTE2(qword_14043B818) |= 2u;
        }
        if ( (v3 & 0x1C0000) != 0 )
        {
          v7 = (((unsigned int)v5 >> 18) & 3) + 4;
          if ( v2 == 8 )
            v7 = ((unsigned int)v5 >> 18) & 3;
          if ( (v5 & 0x100000) == 0 )
            v7 = ((unsigned int)v5 >> 18) & 3;
          LODWORD(v9) = v7;
          sub_140373764(10);
          v5 &= 0x1C0000u;
          qword_14043B818 |= v5;
        }
        if ( v2 != 8 )
        {
          if ( (v3 & 0x4000) != 0 )
          {
            LODWORD(v9) = 3;
            sub_140373764(2);
            BYTE1(qword_14043B818) |= 0x40u;
          }
          v3 = -(__int64)(v3 & 0x8000000000020000uLL);
          if ( !(((unsigned int)v2 < 0xB) | !__OFSUB__(v3, 1)) )
          {
            LODWORD(v9) = 8;
            sub_140373764(8);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400b4aca  push    r15
0x1400b4acc  push    r14
0x1400b4ace  push    rsi
0x1400b4acf  push    rdi
0x1400b4ad0  push    rbx
0x1400b4ad1  sub     rsp, 40h
0x1400b4ad5  mov     rax, cs:__security_cookie
0x1400b4adc  xor     rax, rsp
0x1400b4adf  mov     [rsp+68h+var_30], rax
0x1400b4ae4  mov     r15, rdx
0x1400b4ae7  or      r15, rcx
0x1400b4aea  mov     sil, 1
0x1400b4aed  cmp     r15, rcx
0x1400b4af0  jz      loc_1400B4BF9
0x1400b4af6  mov     rdi, rdx
0x1400b4af9  call    sub_140086090
0x1400b4afe  mov     ebx, eax
0x1400b4b00  bt      edi, 9
0x1400b4b04  jb      loc_1401B7F03
0x1400b4b0a  test    dil, 20h
0x1400b4b0e  jnz     loc_1401B7F45
0x1400b4b14  bt      edi, 0Ah
0x1400b4b18  jnb     short loc_1400B4B6B
0x1400b4b1a  xorps   xmm0, xmm0
0x1400b4b1d  lea     r14, [rsp+68h+var_48]
0x1400b4b22  movaps  xmmword ptr [r14], xmm0
0x1400b4b26  mov     rcx, r14
0x1400b4b29  xor     edx, edx
0x1400b4b2b  mov     r8d, 0A0000h
0x1400b4b31  call    sub_14010BDF0
0x1400b4b36  cmp     byte ptr [r14+8], 1
0x1400b4b3b  jnz     loc_1401B7F79
0x1400b4b41  lea     rcx, [rsp+68h+var_48]
0x1400b4b46  call    sub_1400B4C1F
0x1400b4b4b  test    eax, eax
0x1400b4b4d  jnz     loc_1401B7F68
0x1400b4b53  or      byte ptr cs:qword_14043B818+1, 4
0x1400b4b5a  cmp     [rsp+68h+var_40], 1
0x1400b4b5f  jnz     short loc_1400B4B6B
0x1400b4b61  lea     rcx, [rsp+68h+var_48]
0x1400b4b66  call    sub_14010BDC0
0x1400b4b6b  test    dil, 8
0x1400b4b6f  jnz     loc_1401B80BF
0x1400b4b75  bt      edi, 8
0x1400b4b79  jb      loc_1401B7F9A
0x1400b4b7f  bt      edi, 0Bh
0x1400b4b83  jb      loc_1401B7FBB
0x1400b4b89  bt      edi, 0Ch
0x1400b4b8d  jb      loc_1401B7FDC
0x1400b4b93  bt      edi, 0Dh
0x1400b4b97  jb      loc_1401B7FFD
0x1400b4b9d  bt      edi, 10h
0x1400b4ba1  jb      loc_1401B801E
0x1400b4ba7  cmp     ebx, 8
0x1400b4baa  jl      short loc_1400B4BF9
0x1400b4bac  bt      edi, 11h
0x1400b4bb0  jb      loc_1401B803F
0x1400b4bb6  test    edi, 1C0000h
0x1400b4bbc  jnz     loc_1401B8081
0x1400b4bc2  cmp     ebx, 8
0x1400b4bc5  jz      short loc_1400B4BF9
0x1400b4bc7  bt      edi, 0Eh
0x1400b4bcb  jb      loc_1401B8060
0x1400b4bd1  cmp     ebx, 0Bh
0x1400b4bd4  setb    al
0x1400b4bd7  mov     rcx, 8000000000000000h
0x1400b4be1  or      rcx, 20000h
0x1400b4be8  and     rdi, rcx
0x1400b4beb  neg     rdi
0x1400b4bee  setno   cl
0x1400b4bf1  or      cl, al
0x1400b4bf3  jz      loc_1401B7F80
0x1400b4bf9  mov     rax, [rsp+68h+var_30]
0x1400b4bfe  xor     rax, rsp
0x1400b4c01  mov     rcx, cs:__security_cookie
0x1400b4c08  cmp     rcx, rax
0x1400b4c0b  jnz     loc_1401B7EF6
0x1400b4c11  mov     eax, esi
0x1400b4c13  add     rsp, 40h
0x1400b4c17  pop     rbx
0x1400b4c18  pop     rdi
0x1400b4c19  pop     rsi
0x1400b4c1a  pop     r14
0x1400b4c1c  pop     r15
0x1400b4c1e  retn
0x1401b7ef6  mov     rcx, [rsp+68h+var_30]
0x1401b7efb  xor     rcx, rsp; StackCookie
0x1401b7efe  call    __security_check_cookie
0x1401b7f03  mov     ecx, 0C00h; DirectoryFlags
0x1401b7f08  call    cs:SetDefaultDllDirectories
0x1401b7f0e  test    eax, eax
0x1401b7f10  jz      short loc_1401B7F1E
0x1401b7f12  or      byte ptr cs:qword_14043B818+1, 2
0x1401b7f19  jmp     loc_1400B4B0A
0x1401b7f1e  call    cs:__imp_GetLastError
0x1401b7f24  cmp     eax, 57h ; 'W'
0x1401b7f27  jnz     short loc_1401B7F38
0x1401b7f29  mov     ecx, 800h; DirectoryFlags
0x1401b7f2e  call    cs:SetDefaultDllDirectories
0x1401b7f34  test    eax, eax
0x1401b7f36  jnz     short loc_1401B7F12
0x1401b7f38  call    cs:__imp_GetLastError
0x1401b7f3e  cmp     eax, 5
0x1401b7f41  jz      short loc_1401B7F12
0x1401b7f43  jmp     short loc_1401B7F79
0x1401b7f45  xor     ecx, ecx; HeapHandle
0x1401b7f47  mov     edx, 1; HeapInformationClass
0x1401b7f4c  xor     r8d, r8d; HeapInformation
0x1401b7f4f  xor     r9d, r9d; HeapInformationLength
0x1401b7f52  call    cs:HeapSetInformation
0x1401b7f58  test    eax, eax
0x1401b7f5a  jz      short loc_1401B7F79
0x1401b7f5c  or      byte ptr cs:qword_14043B818, 20h
0x1401b7f63  jmp     loc_1400B4B14
0x1401b7f68  cmp     [rsp+68h+var_40], 1
0x1401b7f6d  jnz     short loc_1401B7F79
0x1401b7f6f  lea     rcx, [rsp+68h+var_48]
0x1401b7f74  call    sub_14010BDC0
0x1401b7f79  xor     esi, esi
0x1401b7f7b  jmp     loc_1400B4BF9
0x1401b7f80  lea     rdx, [rsp+68h+var_48]
0x1401b7f85  mov     dword ptr [rdx], 8
0x1401b7f8b  mov     ecx, 8
0x1401b7f90  call    sub_140373764
0x1401b7f95  jmp     loc_1400B4BF9
0x1401b7f9a  lea     rdx, [rsp+68h+var_48]
0x1401b7f9f  mov     dword ptr [rdx], 3
0x1401b7fa5  mov     ecx, 3
0x1401b7faa  call    sub_140373764
0x1401b7faf  or      byte ptr cs:qword_14043B818+1, 1
0x1401b7fb6  jmp     loc_1400B4B7F
0x1401b7fbb  lea     rdx, [rsp+68h+var_48]
0x1401b7fc0  mov     dword ptr [rdx], 1
0x1401b7fc6  mov     ecx, 4
0x1401b7fcb  call    sub_140373764
0x1401b7fd0  or      byte ptr cs:qword_14043B818+1, 8
0x1401b7fd7  jmp     loc_1400B4B89
0x1401b7fdc  lea     rdx, [rsp+68h+var_48]
0x1401b7fe1  mov     dword ptr [rdx], 1
0x1401b7fe7  mov     ecx, 6
0x1401b7fec  call    sub_140373764
0x1401b7ff1  or      byte ptr cs:qword_14043B818+1, 10h
0x1401b7ff8  jmp     loc_1400B4B93
0x1401b7ffd  lea     rdx, [rsp+68h+var_48]
0x1401b8002  mov     dword ptr [rdx], 1
0x1401b8008  mov     ecx, 2
0x1401b800d  call    sub_140373764
0x1401b8012  or      byte ptr cs:qword_14043B818+1, 20h
0x1401b8019  jmp     loc_1400B4B9D
0x1401b801e  lea     rdx, [rsp+68h+var_48]
0x1401b8023  mov     dword ptr [rdx], 1
0x1401b8029  mov     ecx, 9
0x1401b802e  call    sub_140373764
0x1401b8033  or      byte ptr cs:qword_14043B818+2, 1
0x1401b803a  jmp     loc_1400B4BA7
0x1401b803f  lea     rdx, [rsp+68h+var_48]
0x1401b8044  mov     dword ptr [rdx], 1
0x1401b804a  mov     ecx, 8
0x1401b804f  call    sub_140373764
0x1401b8054  or      byte ptr cs:qword_14043B818+2, 2
0x1401b805b  jmp     loc_1400B4BB6
0x1401b8060  lea     rdx, [rsp+68h+var_48]
0x1401b8065  mov     dword ptr [rdx], 3
0x1401b806b  mov     ecx, 2
0x1401b8070  call    sub_140373764
0x1401b8075  or      byte ptr cs:qword_14043B818+1, 40h
0x1401b807c  jmp     loc_1400B4BD1
0x1401b8081  mov     eax, r15d
0x1401b8084  shr     eax, 12h
0x1401b8087  and     eax, 3
0x1401b808a  lea     ecx, [rax+4]
0x1401b808d  cmp     ebx, 8
0x1401b8090  cmovz   ecx, eax
0x1401b8093  bt      r15d, 14h
0x1401b8098  cmovnb  ecx, eax
0x1401b809b  lea     rdx, [rsp+68h+var_48]
0x1401b80a0  mov     [rdx], ecx
0x1401b80a2  mov     ecx, 0Ah
0x1401b80a7  call    sub_140373764
0x1401b80ac  and     r15d, 1C0000h
0x1401b80b3  or      cs:qword_14043B818, r15
0x1401b80ba  jmp     loc_1400B4BC2
0x1401b80bf  mov     eax, r15d
0x1401b80c2  shr     eax, 1
0x1401b80c4  and     eax, 8
0x1401b80c7  mov     ecx, r15d
0x1401b80ca  shr     ecx, 6
0x1401b80cd  and     ecx, 1
0x1401b80d0  or      ecx, eax
0x1401b80d2  mov     eax, r15d
0x1401b80d5  shr     eax, 5
0x1401b80d8  and     eax, 4
0x1401b80db  add     eax, ecx
0x1401b80dd  add     eax, 2
0x1401b80e0  lea     rdx, [rsp+68h+var_48]
0x1401b80e5  mov     [rdx], eax
0x1401b80e7  mov     ecx, 1
0x1401b80ec  call    sub_140373764
0x1401b80f1  mov     eax, r15d
0x1401b80f4  and     eax, 0D8h
0x1401b80f9  or      cs:qword_14043B818, rax
0x1401b8100  jmp     loc_1400B4B75
```
