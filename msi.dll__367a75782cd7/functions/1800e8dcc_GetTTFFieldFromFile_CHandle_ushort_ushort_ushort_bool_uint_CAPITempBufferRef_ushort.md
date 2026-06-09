# GetTTFFieldFromFile(CHandle &,ushort,ushort,ushort,bool,uint,CAPITempBufferRef<ushort> &)

- ea: `0x1800e8dcc`
- end: `0x1800e914e`
- name: `?GetTTFFieldFromFile@@YAKAEAVCHandle@@GGG_NIAEAV?$CAPITempBufferRef@G@@@Z`
- size: `898`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800e8cac`
- `0x1801462ac`

## callees

- `0x180071fdc`
- `0x1800e8dcc`
- `0x180216728`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800e8e64`
- `KERNEL32!ReadFile` at `0x1800e8ecc`
- `KERNEL32!ReadFile` at `0x1800e8f40`
- `KERNEL32!ReadFile` at `0x1800e8f87`
- `KERNEL32!ReadFile` at `0x1800e90ef`
- `KERNEL32!ReadFile` at `0x1800e8e64`
- `KERNEL32!ReadFile` at `0x1800e8ecc`
- `KERNEL32!ReadFile` at `0x1800e8f40`
- `KERNEL32!ReadFile` at `0x1800e8f87`
- `KERNEL32!ReadFile` at `0x1800e90ef`
- `KERNEL32!SetFilePointer` at `0x1800e8e3d`
- `KERNEL32!SetFilePointer` at `0x1800e8f1c`
- `KERNEL32!SetFilePointer` at `0x1800e90cb`
- `KERNEL32!SetFilePointer` at `0x1800e8e3d`
- `KERNEL32!SetFilePointer` at `0x1800e8f1c`
- `KERNEL32!SetFilePointer` at `0x1800e90cb`

## pseudocode

```c
__int64 __fastcall GetTTFFieldFromFile(
        HANDLE *a1,
        __int64 a2,
        __int16 a3,
        __int16 a4,
        char a5,
        unsigned int a6,
        void **a7)
{
  HANDLE v9; // rcx
  HANDLE v11; // rcx
  unsigned int v13; // ebx
  unsigned int v14; // esi
  LONG v15; // ebx
  int i; // ebx
  __int16 v17; // r15
  __int16 v18; // r12
  int v19; // r13d
  int v20; // ebx
  DWORD v21; // r14d
  unsigned int v22; // esi
  LONG v23; // ebx
  char *v24; // rsi
  int j; // r9d
  __int64 v26; // rdx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-71h] BYREF
  int v28; // [rsp+34h] [rbp-6Dh] BYREF
  unsigned __int16 v29; // [rsp+38h] [rbp-69h]
  int v30; // [rsp+3Ch] [rbp-65h]
  int v31; // [rsp+40h] [rbp-61h]
  int v32; // [rsp+44h] [rbp-5Dh]
  void **v33; // [rsp+48h] [rbp-59h]
  __int64 v34; // [rsp+50h] [rbp-51h] BYREF
  int v35; // [rsp+58h] [rbp-49h]
  __int128 v36; // [rsp+60h] [rbp-41h] BYREF
  _BYTE Buffer[32]; // [rsp+70h] [rbp-31h] BYREF

  v33 = a7;
  v9 = *a1;
  v28 = 0;
  memset(Buffer, 0, 28);
  v29 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  if ( a5 )
  {
    if ( !FTTCSeek(v9, a6) )
      return 0;
  }
  else if ( SetFilePointer(v9, 0, 0, 0) )
  {
    return 0;
  }
  v11 = *a1;
  NumberOfBytesRead = 0;
  if ( ReadFile(v11, Buffer, 0xCu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 12 )
  {
    v13 = 0;
    v14 = Buffer[5] | (unsigned __int16)(Buffer[4] << 8);
    while ( v13 < v14 && v13 < 0x28 && ReadFile(*a1, &v36, 0x10u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 16 )
    {
      if ( (_DWORD)v36 == 1701667182 )
      {
        v15 = ((WORD4(v36) & 0xFF00 | (DWORD2(v36) << 16)) << 8)
            | ((HIWORD(DWORD2(v36)) | DWORD2(v36) & 0xFF0000u) >> 8);
        if ( SetFilePointer(*a1, v15, 0, 0) == v15
          && ReadFile(*a1, &v28, 6u, &NumberOfBytesRead, 0)
          && NumberOfBytesRead == 6 )
        {
          for ( i = HIBYTE(HIWORD(v28)) | (unsigned __int16)(BYTE2(v28) << 8);
                i && ReadFile(*a1, &v34, 0xCu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 12;
                --i )
          {
            if ( (BYTE1(v34) | (unsigned __int16)((unsigned __int8)v34 << 8)) == 3
              && ((HIBYTE(WORD2(v34)) | (unsigned __int16)(BYTE4(v34) << 8)) == a3
               && (HIBYTE(HIWORD(v34)) | (unsigned __int16)(BYTE6(v34) << 8)) == a4
               || (HIBYTE(HIWORD(v34)) | (unsigned __int16)(BYTE6(v34) << 8)) == a4 && a3 == 2048) )
            {
              v17 = (unsigned __int8)v29;
              v18 = BYTE2(v35);
              v19 = DWORD2(v36) & 0xFF0000;
              v30 = DWORD2(v36) << 16;
              v20 = WORD4(v36) & 0xFF00;
              v31 = HIBYTE(v29);
              v32 = HIBYTE(HIWORD(v35));
              v21 = BYTE1(v35) | (unsigned __int16)((unsigned __int8)v35 << 8);
              v22 = HIWORD(DWORD2(v36));
              if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(v33, (v21 >> 1) + 1, 0) )
                return 0;
              v23 = (v32 | (unsigned __int16)(v18 << 8))
                  + (v31 | (unsigned __int16)(v17 << 8))
                  + (((v19 | v22) >> 8) | ((v30 | v20) << 8));
              v24 = (char *)*v33;
              if ( SetFilePointer(*a1, v23, 0, 0) != v23
                || !ReadFile(*a1, v24, v21, &NumberOfBytesRead, 0)
                || v21 != NumberOfBytesRead )
              {
                return 0;
              }
              for ( j = 0;
                    j < (unsigned __int64)v21 >> 1;
                    *(_WORD *)&v24[2 * v26] = _byteswap_ushort(*(_WORD *)&v24[2 * v26]) )
              {
                v26 = j++;
              }
              *(_WORD *)&v24[v21 & 0xFFFFFFFE] = 0;
              return v21 + 1;
            }
          }
        }
        return 0;
      }
      ++v13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800e8dcc  push    rbp
0x1800e8dce  push    rbx
0x1800e8dcf  push    rsi
0x1800e8dd0  push    rdi
0x1800e8dd1  push    r12
0x1800e8dd3  push    r13
0x1800e8dd5  push    r14
0x1800e8dd7  push    r15
0x1800e8dd9  lea     rbp, [rsp-7]
0x1800e8dde  sub     rsp, 0A8h
0x1800e8de5  mov     rax, cs:__security_cookie
0x1800e8dec  xor     rax, rsp
0x1800e8def  mov     [rbp+3Fh+var_50], rax
0x1800e8df3  mov     rax, [rbp+3Fh+arg_30]
0x1800e8df7  xorps   xmm0, xmm0
0x1800e8dfa  mov     [rbp+3Fh+var_98], rax
0x1800e8dfe  xor     r12d, r12d
0x1800e8e01  xor     eax, eax
0x1800e8e03  mov     rdi, rcx
0x1800e8e06  movzx   r15d, r9w
0x1800e8e0a  mov     rcx, [rcx]; hFile
0x1800e8e0d  movzx   r14d, r8w
0x1800e8e11  mov     [rbp+3Fh+var_AC], eax
0x1800e8e14  movups  xmmword ptr [rbp+3Fh+Buffer], xmm0
0x1800e8e18  mov     [rbp+3Fh+var_A8], ax
0x1800e8e1c  movups  xmmword ptr [rbp+3Fh+Buffer+0Ch], xmm0
0x1800e8e20  mov     [rbp+3Fh+var_90], rax
0x1800e8e24  movups  [rbp+3Fh+var_80], xmm0
0x1800e8e28  mov     [rbp+3Fh+var_88], eax
0x1800e8e2b  cmp     [rbp+3Fh+arg_20], r12b
0x1800e8e2f  jnz     loc_1800E8FBC
0x1800e8e35  xor     r9d, r9d; dwMoveMethod
0x1800e8e38  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800e8e3b  xor     edx, edx; lDistanceToMove
0x1800e8e3d  call    cs:__imp_SetFilePointer
0x1800e8e43  test    eax, eax
0x1800e8e45  jnz     short loc_1800E8E6E
0x1800e8e47  mov     rcx, [rdi]; hFile
0x1800e8e4a  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e8e4e  mov     r13d, 0Ch
0x1800e8e54  mov     [rbp+3Fh+NumberOfBytesRead], r12d
0x1800e8e58  mov     r8d, r13d; nNumberOfBytesToRead
0x1800e8e5b  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800e8e60  lea     rdx, [rbp+3Fh+Buffer]; lpBuffer
0x1800e8e64  call    cs:__imp_ReadFile
0x1800e8e6a  test    eax, eax
0x1800e8e6c  jnz     short loc_1800E8E90
0x1800e8e6e  xor     eax, eax
0x1800e8e70  mov     rcx, [rbp+3Fh+var_50]
0x1800e8e74  xor     rcx, rsp; StackCookie
0x1800e8e77  call    __security_check_cookie
0x1800e8e7c  add     rsp, 0A8h
0x1800e8e83  pop     r15
0x1800e8e85  pop     r14
0x1800e8e87  pop     r13
0x1800e8e89  pop     r12
0x1800e8e8b  pop     rdi
0x1800e8e8c  pop     rsi
0x1800e8e8d  pop     rbx
0x1800e8e8e  pop     rbp
0x1800e8e8f  retn
0x1800e8e90  cmp     [rbp+3Fh+NumberOfBytesRead], r13d
0x1800e8e94  jnz     short loc_1800E8E6E
0x1800e8e96  movzx   eax, [rbp+3Fh+Buffer+4]
0x1800e8e9a  mov     ebx, r12d
0x1800e8e9d  shl     ax, 8
0x1800e8ea1  movzx   esi, ax
0x1800e8ea4  movzx   eax, word ptr [rbp+3Fh+Buffer+4]
0x1800e8ea8  shr     eax, 8
0x1800e8eab  or      esi, eax
0x1800e8ead  cmp     ebx, esi
0x1800e8eaf  jnb     short loc_1800E8E6E
0x1800e8eb1  cmp     ebx, 28h ; '('
0x1800e8eb4  jnb     short loc_1800E8E6E
0x1800e8eb6  mov     rcx, [rdi]; hFile
0x1800e8eb9  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e8ebd  mov     r8d, 10h; nNumberOfBytesToRead
0x1800e8ec3  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800e8ec8  lea     rdx, [rbp+3Fh+var_80]; lpBuffer
0x1800e8ecc  call    cs:__imp_ReadFile
0x1800e8ed2  test    eax, eax
0x1800e8ed4  jz      short loc_1800E8E6E
0x1800e8ed6  cmp     [rbp+3Fh+NumberOfBytesRead], 10h
0x1800e8eda  jnz     short loc_1800E8E6E
0x1800e8edc  cmp     dword ptr [rbp+3Fh+var_80], 656D616Eh
0x1800e8ee3  jz      short loc_1800E8EE9
0x1800e8ee5  inc     ebx
0x1800e8ee7  jmp     short loc_1800E8EAD
0x1800e8ee9  mov     ecx, dword ptr [rbp+3Fh+var_80+8]
0x1800e8eec  mov     esi, 0FF0000h
0x1800e8ef1  mov     ebx, ecx
0x1800e8ef3  mov     eax, ecx
0x1800e8ef5  shr     eax, 10h
0x1800e8ef8  and     ebx, esi
0x1800e8efa  or      ebx, eax
0x1800e8efc  xor     r9d, r9d; dwMoveMethod
0x1800e8eff  mov     eax, ecx
0x1800e8f01  shr     ebx, 8
0x1800e8f04  shl     eax, 10h
0x1800e8f07  and     ecx, 0FF00h
0x1800e8f0d  or      eax, ecx
0x1800e8f0f  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800e8f12  mov     rcx, [rdi]; hFile
0x1800e8f15  shl     eax, 8
0x1800e8f18  or      ebx, eax
0x1800e8f1a  mov     edx, ebx; lDistanceToMove
0x1800e8f1c  call    cs:__imp_SetFilePointer
0x1800e8f22  cmp     eax, ebx
0x1800e8f24  jnz     loc_1800E8E6E
0x1800e8f2a  mov     rcx, [rdi]; hFile
0x1800e8f2d  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e8f31  mov     r8d, 6; nNumberOfBytesToRead
0x1800e8f37  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800e8f3c  lea     rdx, [rbp+3Fh+var_AC]; lpBuffer
0x1800e8f40  call    cs:__imp_ReadFile
0x1800e8f46  test    eax, eax
0x1800e8f48  jz      loc_1800E8E6E
0x1800e8f4e  cmp     [rbp+3Fh+NumberOfBytesRead], 6
0x1800e8f52  jnz     loc_1800E8E6E
0x1800e8f58  movzx   eax, byte ptr [rbp+3Fh+var_AC+2]
0x1800e8f5c  shl     ax, 8
0x1800e8f60  movzx   ebx, ax
0x1800e8f63  movzx   eax, word ptr [rbp+3Fh+var_AC+2]
0x1800e8f67  shr     eax, 8
0x1800e8f6a  or      ebx, eax
0x1800e8f6c  test    ebx, ebx
0x1800e8f6e  jz      loc_1800E8E6E
0x1800e8f74  mov     rcx, [rdi]; hFile
0x1800e8f77  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e8f7b  mov     r8d, r13d; nNumberOfBytesToRead
0x1800e8f7e  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800e8f83  lea     rdx, [rbp+3Fh+var_90]; lpBuffer
0x1800e8f87  call    cs:__imp_ReadFile
0x1800e8f8d  test    eax, eax
0x1800e8f8f  jz      loc_1800E8E6E
0x1800e8f95  cmp     [rbp+3Fh+NumberOfBytesRead], r13d
0x1800e8f99  jnz     loc_1800E8E6E
0x1800e8f9f  movzx   ecx, byte ptr [rbp+3Fh+var_90]
0x1800e8fa3  movzx   eax, word ptr [rbp+3Fh+var_90]
0x1800e8fa7  shl     cx, 8
0x1800e8fab  shr     ax, 8
0x1800e8faf  or      cx, ax
0x1800e8fb2  cmp     cx, 3
0x1800e8fb6  jz      short loc_1800E8FD1
0x1800e8fb8  dec     ebx
0x1800e8fba  jmp     short loc_1800E8F6C
0x1800e8fbc  mov     edx, [rbp+3Fh+arg_28]; unsigned int
0x1800e8fbf  call    ?FTTCSeek@@YA_NPEAXI@Z; FTTCSeek(void *,uint)
0x1800e8fc4  test    al, al
0x1800e8fc6  jz      loc_1800E8E6E
0x1800e8fcc  jmp     loc_1800E8E47
0x1800e8fd1  movzx   ecx, byte ptr [rbp+3Fh+var_90+4]
0x1800e8fd5  movzx   eax, word ptr [rbp+3Fh+var_90+4]
0x1800e8fd9  movzx   edx, word ptr [rbp+3Fh+var_90+6]
0x1800e8fdd  shl     cx, 8
0x1800e8fe1  shr     ax, 8
0x1800e8fe5  or      cx, ax
0x1800e8fe8  cmp     cx, r14w
0x1800e8fec  jnz     short loc_1800E9005
0x1800e8fee  movzx   ecx, dl
0x1800e8ff1  movzx   eax, dx
0x1800e8ff4  shl     cx, 8
0x1800e8ff8  shr     ax, 8
0x1800e8ffc  or      cx, ax
0x1800e8fff  cmp     cx, r15w
0x1800e9003  jz      short loc_1800E9024
0x1800e9005  movzx   eax, dl
0x1800e9008  shl     ax, 8
0x1800e900c  shr     dx, 8
0x1800e9010  or      ax, dx
0x1800e9013  cmp     ax, r15w
0x1800e9017  jnz     short loc_1800E8FB8
0x1800e9019  mov     eax, 800h
0x1800e901e  cmp     ax, r14w
0x1800e9022  jnz     short loc_1800E8FB8
0x1800e9024  mov     ebx, dword ptr [rbp+3Fh+var_80+8]
0x1800e9027  xor     r8d, r8d
0x1800e902a  mov     rcx, [rbp+3Fh+var_98]
0x1800e902e  mov     eax, ebx
0x1800e9030  movzx   r15d, byte ptr [rbp+3Fh+var_A8]
0x1800e9035  mov     r13d, ebx
0x1800e9038  movzx   r12d, byte ptr [rbp+3Fh+var_88+2]
0x1800e903d  and     r13d, esi
0x1800e9040  shl     eax, 10h
0x1800e9043  mov     esi, ebx
0x1800e9045  mov     [rbp+3Fh+var_A4], eax
0x1800e9048  and     ebx, 0FF00h
0x1800e904e  movzx   eax, [rbp+3Fh+var_A8]
0x1800e9052  shr     eax, 8
0x1800e9055  mov     [rbp+3Fh+var_A0], eax
0x1800e9058  movzx   eax, word ptr [rbp+3Fh+var_88+2]
0x1800e905c  shr     eax, 8
0x1800e905f  mov     [rbp+3Fh+var_9C], eax
0x1800e9062  movzx   eax, byte ptr [rbp+3Fh+var_88]
0x1800e9066  shl     ax, 8
0x1800e906a  movzx   r14d, ax
0x1800e906e  movzx   eax, word ptr [rbp+3Fh+var_88]
0x1800e9072  shr     eax, 8
0x1800e9075  or      r14d, eax
0x1800e9078  shr     esi, 10h
0x1800e907b  mov     edx, r14d
0x1800e907e  shr     edx, 1
0x1800e9080  inc     edx
0x1800e9082  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x1800e9087  test    al, al
0x1800e9089  jz      loc_1800E8E6E
0x1800e908f  or      ebx, [rbp+3Fh+var_A4]
0x1800e9092  or      esi, r13d
0x1800e9095  mov     rcx, [rdi]; hFile
0x1800e9098  xor     r9d, r9d; dwMoveMethod
0x1800e909b  shl     ebx, 8
0x1800e909e  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800e90a1  shr     esi, 8
0x1800e90a4  or      ebx, esi
0x1800e90a6  shl     r15w, 8
0x1800e90ab  movzx   eax, r15w
0x1800e90af  or      eax, [rbp+3Fh+var_A0]
0x1800e90b2  add     ebx, eax
0x1800e90b4  shl     r12w, 8
0x1800e90b9  movzx   eax, r12w
0x1800e90bd  or      eax, [rbp+3Fh+var_9C]
0x1800e90c0  add     ebx, eax
0x1800e90c2  mov     rax, [rbp+3Fh+var_98]
0x1800e90c6  mov     edx, ebx; lDistanceToMove
0x1800e90c8  mov     rsi, [rax]
0x1800e90cb  call    cs:__imp_SetFilePointer
0x1800e90d1  cmp     eax, ebx
0x1800e90d3  jnz     loc_1800E8E6E
0x1800e90d9  mov     rcx, [rdi]; hFile
0x1800e90dc  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e90e0  mov     r8d, r14d; nNumberOfBytesToRead
0x1800e90e3  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x1800e90ec  mov     rdx, rsi; lpBuffer
0x1800e90ef  call    cs:__imp_ReadFile
0x1800e90f5  test    eax, eax
0x1800e90f7  jz      loc_1800E8E6E
0x1800e90fd  cmp     r14d, [rbp+3Fh+NumberOfBytesRead]
0x1800e9101  jnz     loc_1800E8E6E
0x1800e9107  mov     r10d, r14d
0x1800e910a  mov     r9d, 0
0x1800e9110  shr     r10, 1
0x1800e9113  mov     r8d, r14d
0x1800e9116  jz      short loc_1800E913A
0x1800e9118  movsxd  rdx, r9d
0x1800e911b  inc     r9d
0x1800e911e  movzx   eax, byte ptr [rsi+rdx*2+1]
0x1800e9123  movzx   ecx, byte ptr [rsi+rdx*2]
0x1800e9127  shl     cx, 8
0x1800e912b  or      cx, ax
0x1800e912e  movsxd  rax, r9d
0x1800e9131  mov     [rsi+rdx*2], cx
0x1800e9135  cmp     rax, r10
0x1800e9138  jb      short loc_1800E9118
0x1800e913a  and     r8, 0FFFFFFFFFFFFFFFEh
0x1800e913e  xor     eax, eax
0x1800e9140  mov     [r8+rsi], ax
0x1800e9145  lea     eax, [r14+1]
0x1800e9149  jmp     loc_1800E8E70
```
