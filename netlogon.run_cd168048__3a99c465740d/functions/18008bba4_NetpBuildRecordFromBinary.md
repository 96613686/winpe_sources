# NetpBuildRecordFromBinary

- ea: `0x18008bba4`
- end: `0x18008be96`
- name: `NetpBuildRecordFromBinary`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18008b95c`

## callees

- `0x180003a40`
- `0x18000f3e4`
- `0x18008a5c0`
- `0x18008bba4`
- `0x18008cbc8`
- `0x18008ccf4`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be41`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be51`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be61`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be6f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be41`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be51`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be61`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008be6f`
- `ntdll!RtlLengthSid` at `0x18008bc7d`
- `ntdll!RtlLengthSid` at `0x18008bdab`
- `ntdll!RtlLengthSid` at `0x18008bc7d`
- `ntdll!RtlLengthSid` at `0x18008bdab`

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
0x18008bba4  mov     [rsp-38h+arg_8], rbx
0x18008bba9  mov     [rsp-38h+Src], r8
0x18008bbae  mov     [rsp-38h+arg_0], ecx
0x18008bbb2  push    rbp
0x18008bbb3  push    rsi
0x18008bbb4  push    rdi
0x18008bbb5  push    r12
0x18008bbb7  push    r13
0x18008bbb9  push    r14
0x18008bbbb  push    r15
0x18008bbbd  mov     rbp, rsp
0x18008bbc0  sub     rsp, 70h
0x18008bbc4  mov     rax, [rbp+arg_20]
0x18008bbc8  xor     r15d, r15d
0x18008bbcb  mov     r13d, r9d
0x18008bbce  xorps   xmm0, xmm0
0x18008bbd1  mov     [rbp+Sid], r15
0x18008bbd5  xorps   xmm1, xmm1
0x18008bbd8  mov     rsi, rdx
0x18008bbdb  mov     r14d, r15d
0x18008bbde  mov     [rax], r15
0x18008bbe1  lea     edi, [r15+38h]
0x18008bbe5  mov     dword ptr [rbp+size], edi
0x18008bbe8  movups  xmmword ptr [rbp+Block], xmm0
0x18008bbec  movups  xmmword ptr [rbp+var_18], xmm1
0x18008bbf0  cmp     r9d, 4
0x18008bbf4  jnb     short loc_18008BC00
0x18008bbf6  mov     ebx, 80000005h
0x18008bbfb  jmp     loc_18008BE3E
0x18008bc00  lea     eax, [r13-4]
0x18008bc04  cmp     eax, 1
0x18008bc07  jb      short loc_18008BBF6
0x18008bc09  mov     r9b, [r8+4]
0x18008bc0d  lea     rcx, [r8+5]
0x18008bc11  mov     [rbp+arg_18], r9b
0x18008bc15  lea     edx, [rax-1]
0x18008bc18  mov     [rbp+var_38], rcx
0x18008bc1c  mov     dword ptr [rbp+size+4], edx
0x18008bc1f  cmp     r9b, 3
0x18008bc23  jbe     short loc_18008BBF6
0x18008bc25  cmp     r9b, 4
0x18008bc29  jz      short loc_18008BC51
0x18008bc2b  lea     eax, [r13+38h]
0x18008bc2f  cmp     eax, edi
0x18008bc31  jb      short loc_18008BC47
0x18008bc33  movzx   r12d, word ptr [rbp+Block]
0x18008bc38  mov     edi, eax
0x18008bc3a  movzx   r15d, word ptr [rbp+var_18]
0x18008bc3f  mov     dword ptr [rbp+size], eax
0x18008bc42  jmp     loc_18008BD1F
0x18008bc47  mov     ebx, 0C0000095h
0x18008bc4c  jmp     loc_18008BE3E
0x18008bc51  lea     rax, [rbp+Sid]
0x18008bc55  lea     r9, [rbp+size+4]
0x18008bc59  mov     [rsp+70h+var_50], rax
0x18008bc5e  lea     r8, [rbp+var_38]
0x18008bc62  call    NetpUnmarshalSid
0x18008bc67  mov     r14, [rbp+Sid]
0x18008bc6b  mov     ebx, eax
0x18008bc6d  test    eax, eax
0x18008bc6f  js      loc_18008BE3E
0x18008bc75  test    r14, r14
0x18008bc78  jz      short loc_18008BC94
0x18008bc7a  mov     rcx, r14; Sid
0x18008bc7d  call    cs:__imp_RtlLengthSid
0x18008bc84  nop     dword ptr [rax+rax+00h]
0x18008bc89  add     eax, edi
0x18008bc8b  cmp     eax, edi
0x18008bc8d  jb      short loc_18008BC47
0x18008bc8f  mov     edi, eax
0x18008bc91  mov     dword ptr [rbp+size], eax
0x18008bc94  mov     edx, dword ptr [rbp+size+4]
0x18008bc97  lea     rax, [rbp+Block]
0x18008bc9b  mov     rcx, [rbp+var_38]
0x18008bc9f  lea     r9, [rbp+size+4]
0x18008bca3  lea     r8, [rbp+var_38]
0x18008bca7  mov     [rsp+70h+var_50], rax
0x18008bcac  call    NetpUnmarshalString
0x18008bcb1  mov     ebx, eax
0x18008bcb3  test    eax, eax
0x18008bcb5  js      loc_18008BE3E
0x18008bcbb  movzx   r12d, word ptr [rbp+Block]
0x18008bcc0  test    r12w, r12w
0x18008bcc4  jz      short loc_18008BCDA
0x18008bcc6  mov     ecx, edi
0x18008bcc8  lea     edi, [r12+2]
0x18008bccd  add     edi, ecx
0x18008bccf  cmp     edi, ecx
0x18008bcd1  jb      loc_18008BC47
0x18008bcd7  mov     dword ptr [rbp+size], edi
0x18008bcda  mov     edx, dword ptr [rbp+size+4]
0x18008bcdd  lea     rax, [rbp+var_18]
0x18008bce1  mov     rcx, [rbp+var_38]
0x18008bce5  lea     r9, [rbp+size+4]
0x18008bce9  lea     r8, [rbp+var_38]
0x18008bced  mov     [rsp+70h+var_50], rax
0x18008bcf2  call    NetpUnmarshalString
0x18008bcf7  mov     ebx, eax
0x18008bcf9  test    eax, eax
0x18008bcfb  js      loc_18008BE3E
0x18008bd01  movzx   r15d, word ptr [rbp+var_18]
0x18008bd06  test    r15w, r15w
0x18008bd0a  jz      short loc_18008BD1F
0x18008bd0c  mov     ecx, edi
0x18008bd0e  lea     edi, [r15+2]
0x18008bd12  add     edi, ecx
0x18008bd14  cmp     edi, ecx
0x18008bd16  jb      loc_18008BC47
0x18008bd1c  mov     dword ptr [rbp+size], edi
0x18008bd1f  lea     r8, [rbp+size]
0x18008bd23  mov     ecx, edi
0x18008bd25  call    NetpULongRoundUp
0x18008bd2a  mov     ebx, eax
0x18008bd2c  test    eax, eax
0x18008bd2e  js      loc_18008BE3E
0x18008bd34  mov     ebx, dword ptr [rbp+size]
0x18008bd37  mov     ecx, ebx; size
0x18008bd39  call    MIDL_user_allocate
0x18008bd3e  mov     rdi, rax
0x18008bd41  test    rax, rax
0x18008bd44  jnz     short loc_18008BD50
0x18008bd46  mov     ebx, 0C000009Ah
0x18008bd4b  jmp     loc_18008BE3E
0x18008bd50  mov     r8, rbx; Size
0x18008bd53  xor     edx, edx; Val
0x18008bd55  mov     rcx, rdi; void *
0x18008bd58  call    memset_0
0x18008bd5d  cmp     [rbp+arg_18], 4
0x18008bd61  mov     eax, [rbp+arg_0]
0x18008bd64  mov     [rdi], eax
0x18008bd66  mov     rax, [rsi]
0x18008bd69  lea     rsi, [rdi+38h]
0x18008bd6d  mov     [rdi+8], rax
0x18008bd71  jz      short loc_18008BD99
0x18008bd73  mov     rdx, [rbp+Src]; Src
0x18008bd77  mov     r8, r13; Size
0x18008bd7a  mov     rcx, rsi; void *
0x18008bd7d  mov     dword ptr [rdi+4], 3
0x18008bd84  mov     [rdi+18h], rsi
0x18008bd88  mov     [rdi+10h], r13d
0x18008bd8c  call    memcpy_0
0x18008bd91  xor     r13d, r13d
0x18008bd94  jmp     loc_18008BE34
0x18008bd99  xor     r13d, r13d
0x18008bd9c  mov     dword ptr [rdi+4], 4
0x18008bda3  test    r14, r14
0x18008bda6  jz      short loc_18008BDCE
0x18008bda8  mov     rcx, r14; Sid
0x18008bdab  call    cs:__imp_RtlLengthSid
0x18008bdb2  nop     dword ptr [rax+rax+00h]
0x18008bdb7  mov     rdx, r14; Src
0x18008bdba  mov     [rdi+10h], rsi
0x18008bdbe  mov     r8d, eax; Size
0x18008bdc1  mov     rcx, rsi; void *
0x18008bdc4  mov     ebx, eax
0x18008bdc6  call    memcpy_0
0x18008bdcb  add     rsi, rbx
0x18008bdce  test    r12w, r12w
0x18008bdd2  jz      short loc_18008BE05
0x18008bdd4  mov     rdx, [rbp+Block+8]; Src
0x18008bdd8  lea     eax, [r12+2]
0x18008bddd  movzx   ebx, r12w
0x18008bde1  mov     rcx, rsi; void *
0x18008bde4  mov     r8d, ebx; Size
0x18008bde7  mov     [rdi+20h], rsi
0x18008bdeb  mov     [rdi+1Ah], ax
0x18008bdef  mov     [rdi+18h], r12w
0x18008bdf4  call    memcpy_0
0x18008bdf9  lea     rcx, [rbx+rsi]
0x18008bdfd  mov     [rcx], r13w
0x18008be01  lea     rsi, [rcx+2]
0x18008be05  test    r15w, r15w
0x18008be09  jz      short loc_18008BE34
0x18008be0b  mov     rdx, [rbp+var_18+8]; Src
0x18008be0f  lea     eax, [r15+2]
0x18008be13  movzx   ebx, r15w
0x18008be17  mov     rcx, rsi; void *
0x18008be1a  mov     r8d, ebx; Size
0x18008be1d  mov     [rdi+30h], rsi
0x18008be21  mov     [rdi+2Ah], ax
0x18008be25  mov     [rdi+28h], r15w
0x18008be2a  call    memcpy_0
0x18008be2f  mov     [rbx+rsi], r13w
0x18008be34  mov     rax, [rbp+arg_20]
0x18008be38  mov     ebx, r13d
0x18008be3b  mov     [rax], rdi
0x18008be3e  mov     rcx, r14; Block
0x18008be41  call    cs:__imp_free
0x18008be48  nop     dword ptr [rax+rax+00h]
0x18008be4d  mov     rcx, [rbp+Block+8]; Block
0x18008be51  call    cs:__imp_free
0x18008be58  nop     dword ptr [rax+rax+00h]
0x18008be5d  mov     rcx, [rbp+var_18+8]; Block
0x18008be61  call    cs:__imp_free
0x18008be68  nop     dword ptr [rax+rax+00h]
0x18008be6d  xor     ecx, ecx; Block
0x18008be6f  call    cs:__imp_free
0x18008be76  nop     dword ptr [rax+rax+00h]
0x18008be7b  mov     eax, ebx
0x18008be7d  mov     rbx, [rsp+70h+arg_8]
0x18008be85  add     rsp, 70h
0x18008be89  pop     r15
0x18008be8b  pop     r14
0x18008be8d  pop     r13
0x18008be8f  pop     r12
0x18008be91  pop     rdi
0x18008be92  pop     rsi
0x18008be93  pop     rbp
0x18008be94  retn
```
