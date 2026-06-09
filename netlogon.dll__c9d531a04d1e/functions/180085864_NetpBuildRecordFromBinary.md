# NetpBuildRecordFromBinary

- ea: `0x180085864`
- end: `0x180085b31`
- name: `NetpBuildRecordFromBinary`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180085634`

## callees

- `0x180003950`
- `0x18000ed34`
- `0x1800844d0`
- `0x180085864`
- `0x180086804`
- `0x180086928`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085af5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085aff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085b09`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085b11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085af5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085aff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085b09`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085b11`
- `ntdll!RtlLengthSid` at `0x18008593d`
- `ntdll!RtlLengthSid` at `0x180085a65`
- `ntdll!RtlLengthSid` at `0x18008593d`
- `ntdll!RtlLengthSid` at `0x180085a65`

## pseudocode

```c
__int64 __fastcall NetpBuildRecordFromBinary(int a1, __int64 *a2, _BYTE *a3, unsigned int a4, _QWORD *a5)
{
  size_t v5; // r13
  PSID v7; // r14
  unsigned int v8; // edi
  int v9; // ebx
  unsigned __int8 v10; // r9
  __int64 v11; // rdx
  unsigned __int16 v12; // r12
  unsigned __int16 v13; // r15
  int v14; // eax
  ULONG v15; // eax
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  size_t v18; // rbx
  char *v19; // rax
  char *v20; // rdi
  __int64 v21; // rax
  char *v22; // rsi
  ULONG v23; // eax
  __int64 v24; // rbx
  const void *v25; // rdx
  const void *v26; // rdx
  unsigned int size; // [rsp+30h] [rbp-40h] BYREF
  int size_4; // [rsp+34h] [rbp-3Ch] BYREF
  _BYTE *v30; // [rsp+38h] [rbp-38h] BYREF
  PSID Sid; // [rsp+40h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-28h] BYREF
  void *v33[2]; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 v36; // [rsp+C8h] [rbp+58h]

  v5 = a4;
  Sid = 0;
  v7 = 0;
  *a5 = 0;
  v8 = 56;
  size = 56;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v33 = 0;
  if ( a4 <= 4 || (v10 = a3[4], v36 = v10, v11 = (unsigned int)(v5 - 5), v30 = a3 + 5, size_4 = v5 - 5, v10 <= 3u) )
  {
    v9 = -2147483643;
    goto LABEL_32;
  }
  if ( v10 != 4 )
  {
    if ( (unsigned int)(v5 + 56) >= 0x38 )
    {
      v12 = (unsigned __int16)Block[0];
      v8 = v5 + 56;
      v13 = (unsigned __int16)v33[0];
      size = v5 + 56;
      goto LABEL_20;
    }
    goto LABEL_7;
  }
  v14 = NetpUnmarshalSid((int)a3 + 5, v11, (unsigned int)&v30, (unsigned int)&size_4, (__int64)&Sid);
  v7 = Sid;
  v9 = v14;
  if ( v14 < 0 )
    goto LABEL_32;
  if ( Sid )
  {
    v15 = RtlLengthSid(Sid) + 56;
    if ( v15 < 0x38 )
      goto LABEL_7;
    v8 = v15;
    size = v15;
  }
  v9 = NetpUnmarshalString((_DWORD)v30, size_4, (unsigned int)&v30, (unsigned int)&size_4, (__int64)Block);
  if ( v9 < 0 )
    goto LABEL_32;
  v12 = (unsigned __int16)Block[0];
  if ( LOWORD(Block[0]) )
  {
    v16 = v8;
    v8 += LOWORD(Block[0]) + 2;
    if ( v8 < v16 )
      goto LABEL_7;
    size = v8;
  }
  v9 = NetpUnmarshalString((_DWORD)v30, size_4, (unsigned int)&v30, (unsigned int)&size_4, (__int64)v33);
  if ( v9 < 0 )
    goto LABEL_32;
  v13 = (unsigned __int16)v33[0];
  if ( !LOWORD(v33[0]) )
    goto LABEL_20;
  v17 = v8;
  v8 += LOWORD(v33[0]) + 2;
  if ( v8 < v17 )
  {
LABEL_7:
    v9 = -1073741675;
    goto LABEL_32;
  }
  size = v8;
LABEL_20:
  v9 = NetpULongRoundUp(v8, v11, &size);
  if ( v9 >= 0 )
  {
    v18 = size;
    v19 = (char *)MIDL_user_allocate(size);
    v20 = v19;
    if ( v19 )
    {
      memset_0(v19, 0, v18);
      *(_DWORD *)v20 = a1;
      v21 = *a2;
      v22 = v20 + 56;
      *((_QWORD *)v20 + 1) = v21;
      if ( v36 == 4 )
      {
        *((_DWORD *)v20 + 1) = 4;
        if ( v7 )
        {
          v23 = RtlLengthSid(v7);
          *((_QWORD *)v20 + 2) = v22;
          v24 = v23;
          memcpy_0(v20 + 56, v7, v23);
          v22 += v24;
        }
        if ( v12 )
        {
          v25 = Block[1];
          *((_QWORD *)v20 + 4) = v22;
          *((_WORD *)v20 + 13) = v12 + 2;
          *((_WORD *)v20 + 12) = v12;
          memcpy_0(v22, v25, v12);
          *(_WORD *)&v22[v12] = 0;
          v22 += v12 + 2;
        }
        if ( v13 )
        {
          v26 = v33[1];
          *((_QWORD *)v20 + 6) = v22;
          *((_WORD *)v20 + 21) = v13 + 2;
          *((_WORD *)v20 + 20) = v13;
          memcpy_0(v22, v26, v13);
          *(_WORD *)&v22[v13] = 0;
        }
      }
      else
      {
        *((_DWORD *)v20 + 1) = 3;
        *((_QWORD *)v20 + 3) = v22;
        *((_DWORD *)v20 + 4) = v5;
        memcpy_0(v20 + 56, a3, v5);
      }
      v9 = 0;
      *a5 = v20;
    }
    else
    {
      v9 = -1073741670;
    }
  }
LABEL_32:
  free(v7);
  free(Block[1]);
  free(v33[1]);
  free(0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180085864  mov     [rsp-38h+arg_8], rbx
0x180085869  mov     [rsp-38h+Src], r8
0x18008586e  mov     [rsp-38h+arg_0], ecx
0x180085872  push    rbp
0x180085873  push    rsi
0x180085874  push    rdi
0x180085875  push    r12
0x180085877  push    r13
0x180085879  push    r14
0x18008587b  push    r15
0x18008587d  mov     rbp, rsp
0x180085880  sub     rsp, 70h
0x180085884  mov     rax, [rbp+arg_20]
0x180085888  xor     r15d, r15d
0x18008588b  mov     r13d, r9d
0x18008588e  xorps   xmm0, xmm0
0x180085891  mov     [rbp+Sid], r15
0x180085895  xorps   xmm1, xmm1
0x180085898  mov     rsi, rdx
0x18008589b  mov     r14d, r15d
0x18008589e  mov     [rax], r15
0x1800858a1  lea     edi, [r15+38h]
0x1800858a5  mov     dword ptr [rbp+size], edi
0x1800858a8  movups  xmmword ptr [rbp+Block], xmm0
0x1800858ac  movups  xmmword ptr [rbp+var_18], xmm1
0x1800858b0  cmp     r9d, 4
0x1800858b4  jnb     short loc_1800858C0
0x1800858b6  mov     ebx, 80000005h
0x1800858bb  jmp     loc_180085AF2
0x1800858c0  lea     eax, [r13-4]
0x1800858c4  cmp     eax, 1
0x1800858c7  jb      short loc_1800858B6
0x1800858c9  mov     r9b, [r8+4]
0x1800858cd  lea     rcx, [r8+5]
0x1800858d1  mov     [rbp+arg_18], r9b
0x1800858d5  lea     edx, [rax-1]
0x1800858d8  mov     [rbp+var_38], rcx
0x1800858dc  mov     dword ptr [rbp+size+4], edx
0x1800858df  cmp     r9b, 3
0x1800858e3  jbe     short loc_1800858B6
0x1800858e5  cmp     r9b, 4
0x1800858e9  jz      short loc_180085911
0x1800858eb  lea     eax, [r13+38h]
0x1800858ef  cmp     eax, edi
0x1800858f1  jb      short loc_180085907
0x1800858f3  movzx   r12d, word ptr [rbp+Block]
0x1800858f8  mov     edi, eax
0x1800858fa  movzx   r15d, word ptr [rbp+var_18]
0x1800858ff  mov     dword ptr [rbp+size], eax
0x180085902  jmp     loc_1800859D9
0x180085907  mov     ebx, 0C0000095h
0x18008590c  jmp     loc_180085AF2
0x180085911  lea     rax, [rbp+Sid]
0x180085915  lea     r9, [rbp+size+4]
0x180085919  mov     [rsp+70h+var_50], rax
0x18008591e  lea     r8, [rbp+var_38]
0x180085922  call    NetpUnmarshalSid
0x180085927  mov     r14, [rbp+Sid]
0x18008592b  mov     ebx, eax
0x18008592d  test    eax, eax
0x18008592f  js      loc_180085AF2
0x180085935  test    r14, r14
0x180085938  jz      short loc_18008594E
0x18008593a  mov     rcx, r14; Sid
0x18008593d  call    cs:__imp_RtlLengthSid
0x180085943  add     eax, edi
0x180085945  cmp     eax, edi
0x180085947  jb      short loc_180085907
0x180085949  mov     edi, eax
0x18008594b  mov     dword ptr [rbp+size], eax
0x18008594e  mov     edx, dword ptr [rbp+size+4]
0x180085951  lea     rax, [rbp+Block]
0x180085955  mov     rcx, [rbp+var_38]
0x180085959  lea     r9, [rbp+size+4]
0x18008595d  lea     r8, [rbp+var_38]
0x180085961  mov     [rsp+70h+var_50], rax
0x180085966  call    NetpUnmarshalString
0x18008596b  mov     ebx, eax
0x18008596d  test    eax, eax
0x18008596f  js      loc_180085AF2
0x180085975  movzx   r12d, word ptr [rbp+Block]
0x18008597a  test    r12w, r12w
0x18008597e  jz      short loc_180085994
0x180085980  mov     ecx, edi
0x180085982  lea     edi, [r12+2]
0x180085987  add     edi, ecx
0x180085989  cmp     edi, ecx
0x18008598b  jb      loc_180085907
0x180085991  mov     dword ptr [rbp+size], edi
0x180085994  mov     edx, dword ptr [rbp+size+4]
0x180085997  lea     rax, [rbp+var_18]
0x18008599b  mov     rcx, [rbp+var_38]
0x18008599f  lea     r9, [rbp+size+4]
0x1800859a3  lea     r8, [rbp+var_38]
0x1800859a7  mov     [rsp+70h+var_50], rax
0x1800859ac  call    NetpUnmarshalString
0x1800859b1  mov     ebx, eax
0x1800859b3  test    eax, eax
0x1800859b5  js      loc_180085AF2
0x1800859bb  movzx   r15d, word ptr [rbp+var_18]
0x1800859c0  test    r15w, r15w
0x1800859c4  jz      short loc_1800859D9
0x1800859c6  mov     ecx, edi
0x1800859c8  lea     edi, [r15+2]
0x1800859cc  add     edi, ecx
0x1800859ce  cmp     edi, ecx
0x1800859d0  jb      loc_180085907
0x1800859d6  mov     dword ptr [rbp+size], edi
0x1800859d9  lea     r8, [rbp+size]
0x1800859dd  mov     ecx, edi
0x1800859df  call    NetpULongRoundUp
0x1800859e4  mov     ebx, eax
0x1800859e6  test    eax, eax
0x1800859e8  js      loc_180085AF2
0x1800859ee  mov     ebx, dword ptr [rbp+size]
0x1800859f1  mov     ecx, ebx; size
0x1800859f3  call    MIDL_user_allocate
0x1800859f8  mov     rdi, rax
0x1800859fb  test    rax, rax
0x1800859fe  jnz     short loc_180085A0A
0x180085a00  mov     ebx, 0C000009Ah
0x180085a05  jmp     loc_180085AF2
0x180085a0a  mov     r8, rbx; Size
0x180085a0d  xor     edx, edx; Val
0x180085a0f  mov     rcx, rdi; void *
0x180085a12  call    memset_0
0x180085a17  cmp     [rbp+arg_18], 4
0x180085a1b  mov     eax, [rbp+arg_0]
0x180085a1e  mov     [rdi], eax
0x180085a20  mov     rax, [rsi]
0x180085a23  lea     rsi, [rdi+38h]
0x180085a27  mov     [rdi+8], rax
0x180085a2b  jz      short loc_180085A53
0x180085a2d  mov     rdx, [rbp+Src]; Src
0x180085a31  mov     r8, r13; Size
0x180085a34  mov     rcx, rsi; void *
0x180085a37  mov     dword ptr [rdi+4], 3
0x180085a3e  mov     [rdi+18h], rsi
0x180085a42  mov     [rdi+10h], r13d
0x180085a46  call    memcpy_0
0x180085a4b  xor     r13d, r13d
0x180085a4e  jmp     loc_180085AE8
0x180085a53  xor     r13d, r13d
0x180085a56  mov     dword ptr [rdi+4], 4
0x180085a5d  test    r14, r14
0x180085a60  jz      short loc_180085A82
0x180085a62  mov     rcx, r14; Sid
0x180085a65  call    cs:__imp_RtlLengthSid
0x180085a6b  mov     rdx, r14; Src
0x180085a6e  mov     [rdi+10h], rsi
0x180085a72  mov     r8d, eax; Size
0x180085a75  mov     rcx, rsi; void *
0x180085a78  mov     ebx, eax
0x180085a7a  call    memcpy_0
0x180085a7f  add     rsi, rbx
0x180085a82  test    r12w, r12w
0x180085a86  jz      short loc_180085AB9
0x180085a88  mov     rdx, [rbp+Block+8]; Src
0x180085a8c  lea     eax, [r12+2]
0x180085a91  movzx   ebx, r12w
0x180085a95  mov     rcx, rsi; void *
0x180085a98  mov     r8d, ebx; Size
0x180085a9b  mov     [rdi+20h], rsi
0x180085a9f  mov     [rdi+1Ah], ax
0x180085aa3  mov     [rdi+18h], r12w
0x180085aa8  call    memcpy_0
0x180085aad  lea     rcx, [rbx+rsi]
0x180085ab1  mov     [rcx], r13w
0x180085ab5  lea     rsi, [rcx+2]
0x180085ab9  test    r15w, r15w
0x180085abd  jz      short loc_180085AE8
0x180085abf  mov     rdx, [rbp+var_18+8]; Src
0x180085ac3  lea     eax, [r15+2]
0x180085ac7  movzx   ebx, r15w
0x180085acb  mov     rcx, rsi; void *
0x180085ace  mov     r8d, ebx; Size
0x180085ad1  mov     [rdi+30h], rsi
0x180085ad5  mov     [rdi+2Ah], ax
0x180085ad9  mov     [rdi+28h], r15w
0x180085ade  call    memcpy_0
0x180085ae3  mov     [rbx+rsi], r13w
0x180085ae8  mov     rax, [rbp+arg_20]
0x180085aec  mov     ebx, r13d
0x180085aef  mov     [rax], rdi
0x180085af2  mov     rcx, r14; Block
0x180085af5  call    cs:__imp_free
0x180085afb  mov     rcx, [rbp+Block+8]; Block
0x180085aff  call    cs:__imp_free
0x180085b05  mov     rcx, [rbp+var_18+8]; Block
0x180085b09  call    cs:__imp_free
0x180085b0f  xor     ecx, ecx; Block
0x180085b11  call    cs:__imp_free
0x180085b17  mov     eax, ebx
0x180085b19  mov     rbx, [rsp+70h+arg_8]
0x180085b21  add     rsp, 70h
0x180085b25  pop     r15
0x180085b27  pop     r14
0x180085b29  pop     r13
0x180085b2b  pop     r12
0x180085b2d  pop     rdi
0x180085b2e  pop     rsi
0x180085b2f  pop     rbp
0x180085b30  retn
```
