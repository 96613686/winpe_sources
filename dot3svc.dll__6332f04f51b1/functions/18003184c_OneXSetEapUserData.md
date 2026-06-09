# OneXSetEapUserData

- ea: `0x18003184c`
- end: `0x180031b21`
- name: `OneXSetEapUserData`
- size: `725`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016390`
- `0x180032488`

## callees

- `0x1800030fc`
- `0x180030fd8`
- `0x180031004`
- `0x1800310cc`
- `0x180031584`
- `0x18003184c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a8d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031a83`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031a83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180031924`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180031924`
- `MobileNetworking!FreeMemory` at `0x180031ae1`
- `MobileNetworking!FreeMemory` at `0x180031b01`
- `MobileNetworking!FreeMemory` at `0x180031ae1`
- `MobileNetworking!FreeMemory` at `0x180031b01`

## pseudocode

```c
__int64 __fastcall OneXSetEapUserData(
        void *a1,
        __int64 a2,
        __int128 *a3,
        unsigned int a4,
        void *Src,
        _OWORD *a6,
        unsigned int *a7)
{
  unsigned int *v7; // r15
  __int64 v8; // rsi
  size_t v9; // r13
  void *v10; // r8
  unsigned int v11; // eax
  unsigned int AlignedSize; // ebx
  unsigned int LengthSid; // ebp
  int v14; // r14d
  PSID v15; // r12
  unsigned int v16; // eax
  unsigned int v17; // edi
  _OWORD *v18; // rdi
  _DWORD *v19; // r15
  char *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned int v23; // r10d
  bool v24; // zf
  char *v25; // r9
  __int128 *v26; // r8
  __int128 v27; // xmm0
  unsigned int *v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rax
  void *v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rcx
  unsigned int *v34; // rdx
  PSID *v36; // [rsp+20h] [rbp-48h] BYREF
  __int64 v37[8]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v39; // [rsp+78h] [rbp+10h] BYREF
  __int128 *v40; // [rsp+80h] [rbp+18h]

  v40 = a3;
  v39 = a2;
  v7 = a7;
  v8 = 0;
  v9 = a4;
  v10 = a1;
  v37[0] = 0;
  v36 = 0;
  if ( !a7 )
  {
    AlignedSize = 87;
    goto LABEL_38;
  }
  if ( a2 )
  {
    v8 = a2;
LABEL_6:
    LengthSid = 0;
    v14 = 0;
    v15 = 0;
    v16 = 64;
    if ( !Src || !(_DWORD)v9 )
      goto LABEL_17;
    v14 = v9 + 20;
    if ( (unsigned int)v9 < 0xFFFFFFEC && (int)v9 + 27 >= (unsigned int)(v9 + 20) )
    {
      v17 = ((v9 + 27) & 0xFFFFFFF8) + 64;
      if ( v17 >= 0x40 )
      {
        if ( v10 )
        {
          AlignedSize = OneXGetTokenInformation(v10, (LPVOID *)&v36);
          if ( AlignedSize )
            goto LABEL_38;
          v15 = *v36;
          LengthSid = GetLengthSid(*v36);
        }
        else
        {
          LengthSid = *(_DWORD *)(v8 + 20);
          v15 = (PSID)(v8 + *(unsigned int *)(v8 + 24));
        }
        if ( LengthSid + 7 >= LengthSid )
        {
          v16 = v17 + ((LengthSid + 7) & 0xFFFFFFF8);
          if ( v16 >= v17 )
          {
LABEL_17:
            v18 = a6;
            if ( !a6 )
            {
              *v7 = v16;
              AlignedSize = 234;
              goto LABEL_38;
            }
            if ( *v7 < v16 )
            {
              *v7 = v16;
              AlignedSize = 122;
              goto LABEL_38;
            }
            v19 = (_DWORD *)a6 + 3;
            v20 = (char *)a6 + 12;
            *a6 = *(_OWORD *)v8;
            v18[1] = *(_OWORD *)(v8 + 16);
            v18[2] = *(_OWORD *)(v8 + 32);
            v18[3] = *(_OWORD *)(v8 + 48);
            v21 = *((unsigned int *)v18 + 4);
            *((_DWORD *)v18 + 1) = v16;
            AlignedSize = GetAlignedSize(32, v20, v21);
            if ( AlignedSize )
              goto LABEL_38;
            if ( (unsigned int)(*v19 + v14) >= *v19 )
            {
              v24 = Src == 0;
              v25 = (char *)v18 + v22;
              *v19 += v14;
              if ( v24 || !(_DWORD)v9 )
              {
                *(_DWORD *)v25 &= ~1u;
                AlignedSize = GetAlignedSize(v23, v25 + 28, v22);
                if ( AlignedSize )
                  goto LABEL_38;
                *(_DWORD *)(v32 + 24) = 0;
                *(_OWORD *)(v32 + 4) = 0;
              }
              else
              {
                v26 = v40;
                *(_DWORD *)v25 |= 1u;
                v27 = *v26;
                *(_OWORD *)(v25 + 4) = *v26;
                AlignedSize = GetAlignedSize(v23, v25 + 28, v26);
                if ( AlignedSize )
                  goto LABEL_38;
                v30 = *v28;
                v31 = Src;
                *(_DWORD *)(v29 + 24) = v14;
                *(_DWORD *)(v30 + v29 + 16) = v9;
                *(_OWORD *)(v30 + v29) = v27;
                memcpy_0((void *)(v30 + v29 + 20), v31, v9);
              }
              v33 = (unsigned int)*v19;
              *((_DWORD *)v18 + 6) = *((_DWORD *)v18 + 4);
              AlignedSize = IncrementDwordByAlignedSize(v33);
              if ( !AlignedSize )
              {
                if ( LengthSid )
                {
                  if ( CopySid(LengthSid, (char *)v18 + *v34, v15) || (AlignedSize = GetLastError()) == 0 )
                  {
                    *((_DWORD *)v18 + 2) |= 1u;
                    *((_DWORD *)v18 + 5) = LengthSid;
                  }
                }
                else
                {
                  *((_DWORD *)v18 + 2) &= ~1u;
                  *((_DWORD *)v18 + 5) = 0;
                }
              }
LABEL_38:
              if ( v39 )
                goto LABEL_40;
              goto LABEL_39;
            }
            *v19 = -1;
          }
        }
      }
    }
    AlignedSize = 534;
    goto LABEL_38;
  }
  v11 = OneXCreateDefaultUserProfile(v37, 0, a1);
  v8 = v37[0];
  AlignedSize = v11;
  if ( !v11 )
  {
    v10 = a1;
    goto LABEL_6;
  }
LABEL_39:
  v39 = v8;
  FreeMemory(&v39, "OneXFreeUserProfile", 84);
LABEL_40:
  if ( v36 )
    FreeMemory(&v36, "OneXSetEapUserData", 766);
  return AlignedSize;
}

```

## disassembly

```asm
0x18003184c  mov     rax, rsp
0x18003184f  mov     [rax+20h], rbx
0x180031853  mov     [rax+18h], r8
0x180031857  mov     [rax+10h], rdx
0x18003185b  mov     [rax+8], rcx
0x18003185f  push    rbp
0x180031860  push    rsi
0x180031861  push    rdi
0x180031862  push    r12
0x180031864  push    r13
0x180031866  push    r14
0x180031868  push    r15
0x18003186a  sub     rsp, 30h
0x18003186e  mov     r15, [rsp+68h+arg_30]
0x180031876  xor     esi, esi
0x180031878  mov     r13d, r9d
0x18003187b  mov     r8, rcx
0x18003187e  mov     [rax-40h], rsi
0x180031882  mov     [rax-48h], rsi
0x180031886  test    r15, r15
0x180031889  jz      loc_180031ABD
0x18003188f  test    rdx, rdx
0x180031892  jnz     short loc_1800318B3
0x180031894  lea     rcx, [rax-40h]
0x180031898  call    OneXCreateDefaultUserProfile
0x18003189d  mov     rsi, [rsp+68h+var_40]
0x1800318a2  mov     ebx, eax
0x1800318a4  test    eax, eax
0x1800318a6  jnz     loc_180031ACA
0x1800318ac  mov     r8, [rsp+68h+TokenHandle]
0x1800318b1  jmp     short loc_1800318B6
0x1800318b3  mov     rsi, rdx
0x1800318b6  xor     ebp, ebp
0x1800318b8  xor     r14d, r14d
0x1800318bb  xor     r12d, r12d
0x1800318be  lea     eax, [rbp+40h]
0x1800318c1  cmp     [rsp+68h+Src], rbp
0x1800318c9  jz      loc_180031950
0x1800318cf  test    r13d, r13d
0x1800318d2  jz      short loc_180031950
0x1800318d4  lea     r14d, [r13+14h]
0x1800318d8  cmp     r14d, 14h
0x1800318dc  jb      loc_180031AB6
0x1800318e2  lea     ecx, [r14+7]
0x1800318e6  cmp     ecx, r14d
0x1800318e9  jb      loc_180031AB6
0x1800318ef  and     ecx, 0FFFFFFF8h
0x1800318f2  lea     edi, [rcx+40h]
0x1800318f5  cmp     edi, eax
0x1800318f7  jb      loc_180031AB6
0x1800318fd  test    r8, r8
0x180031900  jz      short loc_18003192E
0x180031902  lea     rdx, [rsp+68h+var_48]
0x180031907  mov     rcx, r8; TokenHandle
0x18003190a  call    OneXGetTokenInformation
0x18003190f  mov     ebx, eax
0x180031911  test    eax, eax
0x180031913  jnz     loc_180031AC2
0x180031919  mov     rax, [rsp+68h+var_48]
0x18003191e  mov     r12, [rax]
0x180031921  mov     rcx, r12; pSid
0x180031924  call    cs:__imp_GetLengthSid
0x18003192a  mov     ebp, eax
0x18003192c  jmp     short loc_180031938
0x18003192e  mov     r12d, [rsi+18h]
0x180031932  mov     ebp, [rsi+14h]
0x180031935  add     r12, rsi
0x180031938  lea     eax, [rbp+7]
0x18003193b  cmp     eax, ebp
0x18003193d  jb      loc_180031AB6
0x180031943  and     eax, 0FFFFFFF8h
0x180031946  add     eax, edi
0x180031948  cmp     eax, edi
0x18003194a  jb      loc_180031AB6
0x180031950  mov     rdi, [rsp+68h+arg_28]
0x180031958  test    rdi, rdi
0x18003195b  jnz     short loc_18003196A
0x18003195d  mov     [r15], eax
0x180031960  mov     ebx, 0EAh
0x180031965  jmp     loc_180031AC2
0x18003196a  cmp     [r15], eax
0x18003196d  jnb     short loc_18003197C
0x18003196f  mov     [r15], eax
0x180031972  mov     ebx, 7Ah ; 'z'
0x180031977  jmp     loc_180031AC2
0x18003197c  movups  xmm0, xmmword ptr [rsi]
0x18003197f  lea     r15, [rdi+0Ch]
0x180031983  mov     r10d, 20h ; ' '
0x180031989  mov     rdx, r15
0x18003198c  mov     ecx, r10d
0x18003198f  movups  xmmword ptr [rdi], xmm0
0x180031992  movups  xmm1, xmmword ptr [rsi+10h]
0x180031996  movups  xmmword ptr [rdi+10h], xmm1
0x18003199a  movups  xmm0, xmmword ptr [rsi+20h]
0x18003199e  movups  xmmword ptr [rdi+20h], xmm0
0x1800319a2  movups  xmm1, xmmword ptr [rsi+30h]
0x1800319a6  movups  xmmword ptr [rdi+30h], xmm1
0x1800319aa  mov     r8d, [rdi+10h]
0x1800319ae  mov     [rdi+4], eax
0x1800319b1  call    GetAlignedSize
0x1800319b6  mov     ebx, eax
0x1800319b8  test    eax, eax
0x1800319ba  jnz     loc_180031AC2
0x1800319c0  mov     eax, [r15]
0x1800319c3  lea     ecx, [rax+r14]
0x1800319c7  cmp     ecx, eax
0x1800319c9  jb      loc_180031AAF
0x1800319cf  cmp     [rsp+68h+Src], 0
0x1800319d8  lea     r9, [rdi+r8]
0x1800319dc  mov     [r15], ecx
0x1800319df  jz      short loc_180031A3C
0x1800319e1  test    r13d, r13d
0x1800319e4  jz      short loc_180031A3C
0x1800319e6  mov     r8, [rsp+68h+arg_10]
0x1800319ee  lea     rdx, [r9+1Ch]
0x1800319f2  or      dword ptr [r9], 1
0x1800319f6  mov     ecx, r10d
0x1800319f9  movaps  xmm0, xmmword ptr [r8]
0x1800319fd  movdqu  xmmword ptr [r9+4], xmm0
0x180031a03  call    GetAlignedSize
0x180031a08  mov     ebx, eax
0x180031a0a  test    eax, eax
0x180031a0c  jnz     loc_180031AC2
0x180031a12  mov     eax, [rdx]
0x180031a14  lea     rcx, [r9+14h]
0x180031a18  mov     rdx, [rsp+68h+Src]; Src
0x180031a20  mov     r8, r13; Size
0x180031a23  mov     [r9+18h], r14d
0x180031a27  add     rcx, rax; void *
0x180031a2a  mov     [rax+r9+10h], r13d
0x180031a2f  movdqu  xmmword ptr [rax+r9], xmm0
0x180031a35  call    memcpy_0
0x180031a3a  jmp     short loc_180031A5E
0x180031a3c  and     dword ptr [r9], 0FFFFFFFEh
0x180031a40  lea     rdx, [r9+1Ch]
0x180031a44  mov     ecx, r10d
0x180031a47  call    GetAlignedSize
0x180031a4c  mov     ebx, eax
0x180031a4e  test    eax, eax
0x180031a50  jnz     short loc_180031AC2
0x180031a52  xorps   xmm0, xmm0
0x180031a55  mov     [r9+18h], eax
0x180031a59  movups  xmmword ptr [r9+4], xmm0
0x180031a5e  mov     eax, [rdi+10h]
0x180031a61  lea     rdx, [rdi+18h]
0x180031a65  mov     ecx, [r15]
0x180031a68  mov     [rdx], eax
0x180031a6a  call    IncrementDwordByAlignedSize
0x180031a6f  mov     ebx, eax
0x180031a71  test    eax, eax
0x180031a73  jnz     short loc_180031AC2
0x180031a75  test    ebp, ebp
0x180031a77  jz      short loc_180031AA2
0x180031a79  mov     edx, [rdx]
0x180031a7b  mov     r8, r12; pSourceSid
0x180031a7e  add     rdx, rdi; pDestinationSid
0x180031a81  mov     ecx, ebp; nDestinationSidLength
0x180031a83  call    cs:__imp_CopySid
0x180031a89  test    eax, eax
0x180031a8b  jnz     short loc_180031A99
0x180031a8d  call    cs:__imp_GetLastError
0x180031a93  mov     ebx, eax
0x180031a95  test    eax, eax
0x180031a97  jnz     short loc_180031AC2
0x180031a99  or      dword ptr [rdi+8], 1
0x180031a9d  mov     [rdi+14h], ebp
0x180031aa0  jmp     short loc_180031AC2
0x180031aa2  and     dword ptr [rdi+8], 0FFFFFFFEh
0x180031aa6  mov     dword ptr [rdi+14h], 0
0x180031aad  jmp     short loc_180031AC2
0x180031aaf  mov     dword ptr [r15], 0FFFFFFFFh
0x180031ab6  mov     ebx, 216h
0x180031abb  jmp     short loc_180031AC2
0x180031abd  mov     ebx, 57h ; 'W'
0x180031ac2  cmp     [rsp+68h+arg_8], 0
0x180031ac8  jnz     short loc_180031AE7
0x180031aca  mov     r8d, 54h ; 'T'
0x180031ad0  mov     [rsp+68h+arg_8], rsi
0x180031ad5  lea     rdx, aOnexfreeuserpr; "OneXFreeUserProfile"
0x180031adc  lea     rcx, [rsp+68h+arg_8]
0x180031ae1  call    cs:__imp_FreeMemory
0x180031ae7  cmp     [rsp+68h+var_48], 0
0x180031aed  jz      short loc_180031B07
0x180031aef  mov     r8d, 2FEh
0x180031af5  lea     rdx, aOnexseteapuser; "OneXSetEapUserData"
0x180031afc  lea     rcx, [rsp+68h+var_48]
0x180031b01  call    cs:__imp_FreeMemory
0x180031b07  mov     eax, ebx
0x180031b09  mov     rbx, [rsp+68h+arg_18]
0x180031b11  add     rsp, 30h
0x180031b15  pop     r15
0x180031b17  pop     r14
0x180031b19  pop     r13
0x180031b1b  pop     r12
0x180031b1d  pop     rdi
0x180031b1e  pop     rsi
0x180031b1f  pop     rbp
0x180031b20  retn
```
