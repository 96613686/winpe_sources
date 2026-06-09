# GetTypeLibResIdList(ushort const *,ulong *,ulong *)

- ea: `0x180058ad4`
- end: `0x180058cdf`
- name: `?GetTypeLibResIdList@@YAJPEBGPEAK1@Z`
- size: `523`
- prototype: `int(const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013900`

## callees

- `0x1800229b8`
- `0x180032130`
- `0x180032668`
- `0x180035560`
- `0x180044c0c`
- `0x18004d900`
- `0x18004e530`
- `0x1800586f8`
- `0x1800589c0`
- `0x180058ad4`

## import_xrefs

- `KERNELBASE!CompareStringA` at `0x180058c4c`
- `KERNELBASE!CompareStringA` at `0x180058c4c`

## pseudocode

```c
__int64 __fastcall GetTypeLibResIdList(const unsigned __int16 *a1, unsigned int *a2, unsigned int *a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rcx
  int TypeLib; // ebx
  __int16 i; // di
  unsigned int v10; // edi
  int v12; // [rsp+30h] [rbp-99h] BYREF
  struct _IMAGE_RESOURCE_DIRECTORY_ENTRY v13; // [rsp+38h] [rbp-91h] BYREF
  __int128 v14; // [rsp+40h] [rbp-89h] BYREF
  int v15; // [rsp+50h] [rbp-79h]
  CHAR String1[16]; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v17[4]; // [rsp+68h] [rbp-61h]
  __int64 v18; // [rsp+78h] [rbp-51h]
  _BYTE v19[8]; // [rsp+80h] [rbp-49h] BYREF
  int v20; // [rsp+88h] [rbp-41h]
  int v21; // [rsp+8Ch] [rbp-3Dh]
  __m128i si128; // [rsp+90h] [rbp-39h]
  int v23; // [rsp+A0h] [rbp-29h]
  int v24; // [rsp+E0h] [rbp+17h]
  int v25; // [rsp+E8h] [rbp+1Fh]

  memset_0(v19, 0, 0x70u);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v12 = 0;
  v20 = -1;
  v21 = 0;
  v23 = 3;
  v25 = 0;
  v6 = FFullyQualified(a1);
  TypeLib = FindTypeLib(v7, (struct LoadInfo *)v19, v6);
  if ( TypeLib >= 0 )
  {
    TypeLib = HrSeek(v20, v24, 0);
    if ( TypeLib >= 0 )
    {
      TypeLib = HrRead(v20, &v12, 4u);
      if ( TypeLib >= 0 )
      {
        if ( v12 == 17744 )
        {
          v15 = 0;
          v14 = 0;
          v18 = 0;
          v13 = 0;
          *(_OWORD *)String1 = 0;
          *(_OWORD *)v17 = 0;
          TypeLib = HrRead(v20, &v14, 0x14u);
          if ( TypeLib >= 0 )
          {
            TypeLib = HrSeek(v20, (unsigned __int16)v15, 1);
            if ( TypeLib >= 0 )
            {
              for ( i = 0; i != WORD1(v14); ++i )
              {
                TypeLib = HrRead(v20, String1, 0x28u);
                if ( TypeLib < 0 )
                  goto LABEL_17;
                if ( CompareStringA(0x7Fu, 1u, String1, -1, ".rsrc", -1) == 2 )
                {
                  v10 = v17[1];
                  TypeLib = GetRsrcDirEntry(v20, v17[1], L"typelib", 0, &v13);
                  if ( TypeLib < 0 )
                    goto LABEL_17;
                  if ( (v13.OffsetToData & 0x80000000) != 0 )
                  {
                    TypeLib = GetRsrcIdList(v20, v10 + (v13.OffsetToData & 0x7FFFFFFF), a2, a3);
                    goto LABEL_17;
                  }
                  break;
                }
              }
              TypeLib = -2147312566;
            }
          }
        }
        else
        {
          *a3 = 0;
        }
      }
    }
  }
LABEL_17:
  UninitLoadInfo((struct LoadInfo *)v19);
  return (unsigned int)TypeLib;
}

```

## disassembly

```asm
0x180058ad4  mov     [rsp-8+arg_18], rbx
0x180058ad9  push    rbp
0x180058ada  push    rsi
0x180058adb  push    rdi
0x180058adc  push    r12
0x180058ade  push    r14
0x180058ae0  lea     rbp, [rsp-37h]
0x180058ae5  sub     rsp, 100h
0x180058aec  mov     rax, cs:__security_cookie
0x180058af3  xor     rax, rsp
0x180058af6  mov     [rbp+57h+var_30], rax
0x180058afa  mov     r14, rdx
0x180058afd  mov     rsi, r8
0x180058b00  xor     edx, edx; Val
0x180058b02  mov     rbx, rcx
0x180058b05  lea     rcx, [rbp+57h+var_A0]; void *
0x180058b09  lea     r8d, [rdx+70h]; Size
0x180058b0d  call    memset_0
0x180058b12  movdqa  xmm0, cs:__xmm@00000000ffffffff0000000000000000
0x180058b1a  mov     rcx, rbx
0x180058b1d  movdqa  [rbp+57h+var_90], xmm0
0x180058b22  mov     [rsp+120h+var_F0], 0
0x180058b2a  mov     [rbp+57h+var_98], 0FFFFFFFFh
0x180058b31  mov     [rbp+57h+var_94], 0
0x180058b38  mov     [rbp+57h+var_80], 3
0x180058b3f  mov     [rbp+57h+var_38], 0
0x180058b46  call    FFullyQualified
0x180058b4b  mov     r8d, eax; int
0x180058b4e  lea     rdx, [rbp+57h+var_A0]; struct LoadInfo *
0x180058b52  call    ?FindTypeLib@@YAJPEBGPEAULoadInfo@@H@Z; FindTypeLib(ushort const *,LoadInfo *,int)
0x180058b57  mov     ebx, eax
0x180058b59  test    eax, eax
0x180058b5b  js      loc_180058CB1
0x180058b61  mov     edx, [rbp+57h+var_40]; int
0x180058b64  xor     r8d, r8d; int
0x180058b67  mov     ecx, [rbp+57h+var_98]; int
0x180058b6a  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058b6f  mov     ebx, eax
0x180058b71  test    eax, eax
0x180058b73  js      loc_180058CB1
0x180058b79  mov     ecx, [rbp+57h+var_98]; int
0x180058b7c  lea     rdx, [rsp+120h+var_F0]; void *
0x180058b81  mov     r8d, 4; unsigned int
0x180058b87  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058b8c  mov     ebx, eax
0x180058b8e  test    eax, eax
0x180058b90  js      loc_180058CB1
0x180058b96  cmp     [rsp+120h+var_F0], 4550h
0x180058b9e  jnz     loc_180058CAB
0x180058ba4  mov     ecx, [rbp+57h+var_98]; int
0x180058ba7  lea     rdx, [rsp+120h+var_E0]; void *
0x180058bac  xor     eax, eax
0x180058bae  xorps   xmm1, xmm1
0x180058bb1  xorps   xmm0, xmm0
0x180058bb4  mov     [rbp+57h+var_D0], eax
0x180058bb7  movups  [rsp+120h+var_E0], xmm0
0x180058bbc  mov     [rbp+57h+var_A8], rax
0x180058bc0  lea     r8d, [rax+14h]; unsigned int
0x180058bc4  mov     qword ptr [rsp+120h+var_E8], rax
0x180058bc9  movups  xmmword ptr [rbp+57h+String1], xmm1
0x180058bcd  movups  xmmword ptr [rbp+57h+var_B8], xmm1
0x180058bd1  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058bd6  mov     ebx, eax
0x180058bd8  test    eax, eax
0x180058bda  js      loc_180058CB1
0x180058be0  movzx   edx, word ptr [rbp+57h+var_D0]; int
0x180058be4  mov     r12d, 1
0x180058bea  mov     ecx, [rbp+57h+var_98]; int
0x180058bed  mov     r8d, r12d; int
0x180058bf0  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058bf5  mov     ebx, eax
0x180058bf7  test    eax, eax
0x180058bf9  js      loc_180058CB1
0x180058bff  xor     edi, edi
0x180058c01  cmp     di, word ptr [rsp+120h+var_E0+2]
0x180058c06  jz      loc_180058CA4
0x180058c0c  mov     ecx, [rbp+57h+var_98]; int
0x180058c0f  lea     rdx, [rbp+57h+String1]; void *
0x180058c13  mov     r8d, 28h ; '('; unsigned int
0x180058c19  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058c1e  mov     ebx, eax
0x180058c20  test    eax, eax
0x180058c22  js      loc_180058CB1
0x180058c28  lea     rax, aRsrc; ".rsrc"
0x180058c2f  mov     [rsp+120h+cchCount2], 0FFFFFFFFh; cchCount2
0x180058c37  or      r9d, 0FFFFFFFFh; cchCount1
0x180058c3b  mov     [rsp+120h+lpString2], rax; lpString2
0x180058c40  lea     r8, [rbp+57h+String1]; lpString1
0x180058c44  mov     edx, r12d; dwCmpFlags
0x180058c47  mov     ecx, 7Fh; Locale
0x180058c4c  call    cs:__imp_CompareStringA
0x180058c52  cmp     eax, 2
0x180058c55  jz      short loc_180058C5D
0x180058c57  add     di, r12w
0x180058c5b  jmp     short loc_180058C01
0x180058c5d  mov     edi, [rbp+57h+var_B8+4]
0x180058c60  lea     rax, [rsp+120h+var_E8]
0x180058c65  mov     ecx, [rbp+57h+var_98]; int
0x180058c68  lea     r8, aTypelib_0; "typelib"
0x180058c6f  mov     edx, edi; unsigned int
0x180058c71  mov     [rsp+120h+lpString2], rax; struct _IMAGE_RESOURCE_DIRECTORY_ENTRY *
0x180058c76  xor     r9d, r9d; unsigned int
0x180058c79  call    ?GetRsrcDirEntry@@YAJHKPEBGKPEAU_IMAGE_RESOURCE_DIRECTORY_ENTRY@@@Z; GetRsrcDirEntry(int,ulong,ushort const *,ulong,_IMAGE_RESOURCE_DIRECTORY_ENTRY *)
0x180058c7e  mov     ebx, eax
0x180058c80  test    eax, eax
0x180058c82  js      short loc_180058CB1
0x180058c84  mov     edx, dword ptr [rsp+120h+var_E8.4]
0x180058c88  test    edx, edx
0x180058c8a  jns     short loc_180058CA4
0x180058c8c  mov     ecx, [rbp+57h+var_98]; int
0x180058c8f  btr     edx, 1Fh
0x180058c93  add     edx, edi; unsigned int
0x180058c95  mov     r9, rsi; unsigned int *
0x180058c98  mov     r8, r14; unsigned int *
0x180058c9b  call    ?GetRsrcIdList@@YAJHKPEAK0@Z; GetRsrcIdList(int,ulong,ulong *,ulong *)
0x180058ca0  mov     ebx, eax
0x180058ca2  jmp     short loc_180058CB1
0x180058ca4  mov     ebx, 80029C4Ah
0x180058ca9  jmp     short loc_180058CB1
0x180058cab  mov     dword ptr [rsi], 0
0x180058cb1  lea     rcx, [rbp+57h+var_A0]; struct LoadInfo *
0x180058cb5  call    ?UninitLoadInfo@@YAXPEAULoadInfo@@@Z; UninitLoadInfo(LoadInfo *)
0x180058cba  mov     eax, ebx
0x180058cbc  mov     rcx, [rbp+57h+var_30]
0x180058cc0  xor     rcx, rsp; StackCookie
0x180058cc3  call    __security_check_cookie
0x180058cc8  mov     rbx, [rsp+120h+arg_18]
0x180058cd0  add     rsp, 100h
0x180058cd7  pop     r14
0x180058cd9  pop     r12
0x180058cdb  pop     rdi
0x180058cdc  pop     rsi
0x180058cdd  pop     rbp
0x180058cde  retn
```
