# CopyOffsetDirectoryTables

- ea: `0x1800079b8`
- end: `0x180007cce`
- name: `CopyOffsetDirectoryTables`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007fa4`

## callees

- `0x1800079b8`
- `0x18000f294`
- `0x180011538`
- `0x180011574`
- `0x180019e64`
- `0x18001a3bc`
- `0x18001a808`
- `0x18001a9c0`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall CopyOffsetDirectoryTables(__int64 a1, __int64 a2, __int16 a3, _DWORD *a4)
{
  unsigned __int16 v4; // si
  unsigned int v7; // r13d
  __int64 result; // rax
  unsigned int v9; // edi
  unsigned __int16 v10; // r14
  __int64 v11; // rbx
  unsigned int v12; // edx
  int i; // eax
  unsigned __int16 Generic; // di
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // r15d
  unsigned int v19; // r14d
  unsigned int v20; // r14d
  _WORD v21[2]; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 v22; // [rsp+44h] [rbp-45h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-41h]
  int v24; // [rsp+4Ch] [rbp-3Dh]
  int v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-31h]
  _DWORD *v27; // [rsp+60h] [rbp-29h]
  __int64 v28; // [rsp+68h] [rbp-21h] BYREF
  int v29; // [rsp+70h] [rbp-19h]
  __int128 v30; // [rsp+78h] [rbp-11h] BYREF
  int v31; // [rsp+88h] [rbp-1h]
  __int128 v32; // [rsp+90h] [rbp+7h] BYREF

  v26 = a2;
  v28 = 0;
  v4 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v21[0] = 0;
  v30 = 0;
  v22 = 0;
  v25 = 0;
  v27 = a4;
  v7 = TTTableOffset(a1, "dttf");
  if ( v7 )
  {
    result = ReadGeneric(a1, (__int64)&v30, 0x12u, (unsigned __int8 *)&DTTF_HEADER_CONTROL, v7, v21);
    if ( (_WORD)result )
      return result;
    if ( WORD6(v30) != 3 )
      return 1013;
  }
  v9 = *(_DWORD *)(a1 + 12);
  result = ReadGeneric(a1, (__int64)&v28, 0xCu, (unsigned __int8 *)&OFFSET_TABLE_CONTROL, v9, v21);
  if ( !(_WORD)result )
  {
    v10 = WORD2(v28);
    if ( WORD2(v28) > 0x3E8u )
      return 1006;
    v11 = Mem_Alloc(16 * (WORD2(v28) + (unsigned __int64)(v7 == 0)));
    if ( !v11 )
      return 1005;
    v12 = v9 + v21[0];
    v23 = v12;
    for ( i = 0; ; LOWORD(i) = v24 + 1 )
    {
      v24 = i;
      if ( (unsigned __int16)i >= v10 )
      {
        if ( !v7 && (unsigned __int16)(a3 - 1) <= 1u )
        {
          v17 = 2LL * v4++;
          *(_QWORD *)(v11 + 8 * v17 + 8) = 0;
          *(_DWORD *)(v11 + 8 * v17) = 1685353574;
          SortByTag(v11, v4);
        }
        v18 = v26;
        WORD2(v28) = v4;
        v19 = *(_DWORD *)(v26 + 12);
        Generic = WriteGeneric(v26, (__int64)&v28, 0xCu, (unsigned __int8 *)&OFFSET_TABLE_CONTROL, v19, &v22);
        if ( !Generic )
        {
          v20 = v22 + v19;
          Generic = WriteGenericRepeat(v18, v11, (unsigned int)&DIRECTORY_CONTROL, v20, (__int64)&v25, v4, 16);
          if ( !Generic )
            *v27 = v20 + v25;
        }
LABEL_40:
        Mem_Free(v11);
        return Generic;
      }
      Generic = ReadGeneric(a1, (__int64)&v32, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v12, v21);
      if ( Generic )
        goto LABEL_40;
      v15 = v32;
      v12 = v21[0] + v23;
      v23 = v12;
      if ( a3 != 2 )
        break;
      if ( (unsigned int)v32 > 0x68646D78 )
      {
        if ( (_DWORD)v32 == 1751474532
          || (_DWORD)v32 == 1751672161
          || (_DWORD)v32 == 1752003704
          || (_DWORD)v32 == 1819239265
          || (_DWORD)v32 == 1835104368
          || (_DWORD)v32 == 1986553185
          || (_DWORD)v32 == 1986884728 )
        {
          break;
        }
      }
      else if ( (_DWORD)v32 == 1751412088
             || (_DWORD)v32 == 1161970772
             || (_DWORD)v32 == 1161972803
             || (_DWORD)v32 == 1280594760
             || (_DWORD)v32 == 1650745716
             || (_DWORD)v32 == 1651273571
             || (_DWORD)v32 == 1668112752
             || (_DWORD)v32 == 1685353574
             || (_DWORD)v32 == 1735162214 )
      {
        break;
      }
LABEL_33:
      HIWORD(i) = HIWORD(v24);
    }
    v16 = 2LL * v4++;
    *(_QWORD *)(v11 + 8 * v16 + 8) = 0;
    *(_DWORD *)(v11 + 8 * v16) = v15;
    goto LABEL_33;
  }
  return result;
}

```

## disassembly

```asm
0x1800079b8  mov     [rsp-8+arg_10], rbx
0x1800079bd  push    rbp
0x1800079be  push    rsi
0x1800079bf  push    rdi
0x1800079c0  push    r12
0x1800079c2  push    r13
0x1800079c4  push    r14
0x1800079c6  push    r15
0x1800079c8  lea     rbp, [rsp-27h]
0x1800079cd  sub     rsp, 0B0h
0x1800079d4  mov     rax, cs:__security_cookie
0x1800079db  xor     rax, rsp
0x1800079de  mov     [rbp+57h+var_40], rax
0x1800079e2  xor     eax, eax
0x1800079e4  mov     [rbp+57h+var_88], rdx
0x1800079e8  xorps   xmm0, xmm0
0x1800079eb  mov     [rbp+57h+var_78], rax
0x1800079ef  xor     esi, esi
0x1800079f1  mov     [rbp+57h+var_70], eax
0x1800079f4  lea     rdx, aDttf; "dttf"
0x1800079fb  mov     [rbp+57h+var_58], eax
0x1800079fe  movups  [rbp+57h+var_50], xmm0
0x180007a02  mov     [rbp+57h+var_A0], si
0x180007a06  movzx   r12d, r8w
0x180007a0a  movups  [rbp+57h+var_68], xmm0
0x180007a0e  mov     [rbp+57h+var_9C], si
0x180007a12  mov     r15, rcx
0x180007a15  mov     [rbp+57h+var_90], esi
0x180007a18  mov     [rbp+57h+var_80], r9
0x180007a1c  call    TTTableOffset
0x180007a21  mov     r13d, eax
0x180007a24  test    eax, eax
0x180007a26  jz      short loc_180007A67
0x180007a28  lea     rax, [rbp+57h+var_A0]
0x180007a2c  mov     rcx, r15
0x180007a2f  mov     [rsp+0E0h+var_B8], rax
0x180007a34  lea     r8d, [rsi+12h]
0x180007a38  lea     r9, DTTF_HEADER_CONTROL
0x180007a3f  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x180007a44  lea     rdx, [rbp+57h+var_68]
0x180007a48  call    ReadGeneric
0x180007a4d  test    ax, ax
0x180007a50  jnz     loc_180007CA7
0x180007a56  cmp     word ptr [rbp+57h+var_68+0Ch], 3
0x180007a5b  jz      short loc_180007A67
0x180007a5d  mov     eax, 3F5h
0x180007a62  jmp     loc_180007CA7
0x180007a67  mov     edi, [r15+0Ch]
0x180007a6b  lea     rax, [rbp+57h+var_A0]
0x180007a6f  mov     [rsp+0E0h+var_B8], rax
0x180007a74  lea     r9, OFFSET_TABLE_CONTROL
0x180007a7b  mov     r8d, 0Ch
0x180007a81  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180007a85  lea     rdx, [rbp+57h+var_78]
0x180007a89  mov     rcx, r15
0x180007a8c  call    ReadGeneric
0x180007a91  test    ax, ax
0x180007a94  jnz     loc_180007CA7
0x180007a9a  movzx   r14d, word ptr [rbp+57h+var_78+4]
0x180007a9f  mov     eax, 3E8h
0x180007aa4  cmp     r14w, ax
0x180007aa8  jbe     short loc_180007AB4
0x180007aaa  mov     eax, 3EEh
0x180007aaf  jmp     loc_180007CA7
0x180007ab4  mov     rcx, rsi
0x180007ab7  test    r13d, r13d
0x180007aba  setz    cl
0x180007abd  add     rcx, r14
0x180007ac0  shl     rcx, 4; Size
0x180007ac4  call    Mem_Alloc
0x180007ac9  mov     rbx, rax
0x180007acc  test    rax, rax
0x180007acf  jnz     short loc_180007ADB
0x180007ad1  mov     eax, 3EDh
0x180007ad6  jmp     loc_180007CA7
0x180007adb  movzx   edx, [rbp+57h+var_A0]
0x180007adf  add     edx, edi
0x180007ae1  xor     r8d, r8d
0x180007ae4  mov     [rbp+57h+var_98], edx
0x180007ae7  mov     eax, r8d
0x180007aea  mov     [rbp+57h+var_94], eax
0x180007aed  mov     ecx, 10h
0x180007af2  cmp     ax, r14w
0x180007af6  jnb     loc_180007BE8
0x180007afc  lea     rax, [rbp+57h+var_A0]
0x180007b00  mov     r8d, ecx
0x180007b03  mov     [rsp+0E0h+var_B8], rax
0x180007b08  lea     r9, DIRECTORY_CONTROL
0x180007b0f  mov     dword ptr [rsp+0E0h+var_C0], edx
0x180007b13  mov     rcx, r15
0x180007b16  lea     rdx, [rbp+57h+var_50]
0x180007b1a  call    ReadGeneric
0x180007b1f  xor     r8d, r8d
0x180007b22  movzx   edi, ax
0x180007b25  test    ax, ax
0x180007b28  jnz     loc_180007C9C
0x180007b2e  mov     edx, [rbp+57h+var_98]
0x180007b31  movzx   eax, [rbp+57h+var_A0]
0x180007b35  mov     ecx, dword ptr [rbp+57h+var_50]
0x180007b38  add     edx, eax
0x180007b3a  mov     [rbp+57h+var_98], edx
0x180007b3d  cmp     r12w, 2
0x180007b42  jnz     loc_180007BCC
0x180007b48  cmp     ecx, 68646D78h
0x180007b4e  ja      short loc_180007B94
0x180007b50  jz      short loc_180007BCC
0x180007b52  cmp     ecx, 45424454h
0x180007b58  jz      short loc_180007BCC
0x180007b5a  cmp     ecx, 45424C43h
0x180007b60  jz      short loc_180007BCC
0x180007b62  cmp     ecx, 4C545348h
0x180007b68  jz      short loc_180007BCC
0x180007b6a  cmp     ecx, 62646174h
0x180007b70  jz      short loc_180007BCC
0x180007b72  cmp     ecx, 626C6F63h
0x180007b78  jz      short loc_180007BCC
0x180007b7a  cmp     ecx, 636D6170h
0x180007b80  jz      short loc_180007BCC
0x180007b82  cmp     ecx, 64747466h
0x180007b88  jz      short loc_180007BCC
0x180007b8a  cmp     ecx, 676C7966h
0x180007b90  jz      short loc_180007BCC
0x180007b92  jmp     short loc_180007BDD
0x180007b94  cmp     ecx, 68656164h
0x180007b9a  jz      short loc_180007BCC
0x180007b9c  cmp     ecx, 68686561h
0x180007ba2  jz      short loc_180007BCC
0x180007ba4  cmp     ecx, 686D7478h
0x180007baa  jz      short loc_180007BCC
0x180007bac  cmp     ecx, 6C6F6361h
0x180007bb2  jz      short loc_180007BCC
0x180007bb4  cmp     ecx, 6D617870h
0x180007bba  jz      short loc_180007BCC
0x180007bbc  cmp     ecx, 76686561h
0x180007bc2  jz      short loc_180007BCC
0x180007bc4  cmp     ecx, 766D7478h
0x180007bca  jnz     short loc_180007BDD
0x180007bcc  movzx   eax, si
0x180007bcf  add     rax, rax
0x180007bd2  inc     si
0x180007bd5  mov     [rbx+rax*8+8], r8
0x180007bda  mov     [rbx+rax*8], ecx
0x180007bdd  mov     eax, [rbp+57h+var_94]
0x180007be0  inc     ax
0x180007be3  jmp     loc_180007AEA
0x180007be8  test    r13d, r13d
0x180007beb  jnz     short loc_180007C1C
0x180007bed  dec     r12w
0x180007bf1  cmp     r12w, 1
0x180007bf6  ja      short loc_180007C1C
0x180007bf8  movzx   eax, si
0x180007bfb  mov     rcx, rbx
0x180007bfe  add     rax, rax
0x180007c01  inc     si
0x180007c04  movzx   edx, si
0x180007c07  mov     qword ptr [rbx+rax*8+8], 0
0x180007c10  mov     dword ptr [rbx+rax*8], 64747466h
0x180007c17  call    SortByTag
0x180007c1c  mov     r15, [rbp+57h+var_88]
0x180007c20  lea     rax, [rbp+57h+var_9C]
0x180007c24  mov     [rsp+0E0h+var_B8], rax
0x180007c29  lea     r9, OFFSET_TABLE_CONTROL
0x180007c30  mov     r8d, 0Ch
0x180007c36  mov     word ptr [rbp+57h+var_78+4], si
0x180007c3a  lea     rdx, [rbp+57h+var_78]
0x180007c3e  mov     rcx, r15
0x180007c41  mov     r14d, [r15+0Ch]
0x180007c45  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x180007c4a  call    WriteGeneric
0x180007c4f  movzx   edi, ax
0x180007c52  test    ax, ax
0x180007c55  jnz     short loc_180007C9C
0x180007c57  movzx   eax, [rbp+57h+var_9C]
0x180007c5b  lea     r8, DIRECTORY_CONTROL
0x180007c62  add     r14d, eax
0x180007c65  mov     [rsp+0E0h+var_B0], 10h
0x180007c6c  lea     rax, [rbp+57h+var_90]
0x180007c70  mov     word ptr [rsp+0E0h+var_B8], si
0x180007c75  mov     r9d, r14d
0x180007c78  mov     [rsp+0E0h+var_C0], rax
0x180007c7d  mov     rdx, rbx
0x180007c80  mov     rcx, r15
0x180007c83  call    WriteGenericRepeat
0x180007c88  movzx   edi, ax
0x180007c8b  test    ax, ax
0x180007c8e  jnz     short loc_180007C9C
0x180007c90  mov     rax, [rbp+57h+var_80]
0x180007c94  mov     ecx, [rbp+57h+var_90]
0x180007c97  add     ecx, r14d
0x180007c9a  mov     [rax], ecx
0x180007c9c  mov     rcx, rbx
0x180007c9f  call    Mem_Free
0x180007ca4  movzx   eax, di
0x180007ca7  mov     rcx, [rbp+57h+var_40]
0x180007cab  xor     rcx, rsp; StackCookie
0x180007cae  call    __security_check_cookie
0x180007cb3  mov     rbx, [rsp+0E0h+arg_10]
0x180007cbb  add     rsp, 0B0h
0x180007cc2  pop     r15
0x180007cc4  pop     r14
0x180007cc6  pop     r13
0x180007cc8  pop     r12
0x180007cca  pop     rdi
0x180007ccb  pop     rsi
0x180007ccc  pop     rbp
0x180007ccd  retn
```
