# GEN_DTINFO::DefineFuncAsDllEntry(uint,ushort *,ushort *)

- ea: `0x18005f300`
- end: `0x18005f4bf`
- name: `?DefineFuncAsDllEntry@GEN_DTINFO@@UEAAJIPEAG0@Z`
- size: `447`
- prototype: `int(GEN_DTINFO *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18003e360`
- `0x18005b7d4`
- `0x18005bba8`
- `0x18005f300`
- `0x18005fd90`
- `0x18005ff38`
- `0x180060550`
- `0x180063130`
- `0x180067508`
- `0x18006b9e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18005f424`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18005f424`

## pseudocode

```c
__int64 __fastcall GEN_DTINFO::DefineFuncAsDllEntry(
        GEN_DTINFO *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax
  int *v9; // rcx
  int v10; // r9d
  struct ENTRYMGR *v11; // r15
  ENTRYMGR *v12; // rcx
  int v13; // eax
  unsigned int v14; // r9d
  __int64 v15; // rdi
  int v16; // ebx
  char *v17; // rsi
  __int64 v18; // rax
  unsigned int v19; // r12d
  __int16 v20; // bx
  struct ENTRYMGR *v21; // rsi
  __int64 v22; // r10
  int *v23; // [rsp+20h] [rbp-48h]
  int v24; // [rsp+28h] [rbp-40h]
  int v25; // [rsp+30h] [rbp-38h]
  unsigned int v26; // [rsp+40h] [rbp-28h] BYREF
  struct ENTRYMGR *v27; // [rsp+48h] [rbp-20h] BYREF
  char *Source; // [rsp+50h] [rbp-18h] BYREF
  struct DYN_TYPEMEMBERS *v29; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v30; // [rsp+C0h] [rbp+58h] BYREF

  v26 = 0;
  Source = 0;
  v27 = 0;
  v30 = 0;
  v29 = 0;
  if ( !a3 )
    return 2147942487LL;
  v9 = (int *)*((_QWORD *)this + 6);
  if ( v9[37] > 0 )
    return 2147647529LL;
  result = DYN_TYPEROOT::GetNamMgr((DYN_TYPEROOT *)v9, (struct NAMMGR **)&Source);
  if ( !(_DWORD)result )
  {
    result = DYN_TYPEROOT::GetEntMgr(*((DYN_TYPEROOT **)this + 6), &v27);
    if ( !(_DWORD)result )
    {
      result = NAMMGR::HlnamOfStrW((NAMMGR *)Source, a3, &v26, v10, v23, v24, v25);
      if ( !(_DWORD)result )
      {
        if ( ((unsigned int)a4 & 0xFFFF0000) != 0 )
        {
          Source = 0;
          result = ConvertStringToA(a4, &Source);
          if ( (_DWORD)result )
            return result;
          v11 = v27;
          v12 = v27;
          LODWORD(v27) = 0;
          v13 = ENTRYMGR::AllocDllentrydefn(v12, &v30, v26, 0);
          v15 = v30;
          v16 = v13;
          v17 = Source;
          if ( v13 >= 0 )
          {
            v18 = -1;
            do
              ++v18;
            while ( Source[v18] );
            v19 = v18 + 1;
            v16 = BLK_MGR::AllocChunk2((struct ENTRYMGR *)((char *)v11 + 16), (unsigned int *)&v27, (int)v18 + 1, v14);
            if ( v16 >= 0 )
            {
              v20 = (__int16)v27;
              strcpy_s((char *)(*((_QWORD *)v11 + 2) + (unsigned int)v27), v19, v17);
              *(_WORD *)(v15 + *((_QWORD *)v11 + 2) + 4) = v20;
              v16 = 0;
            }
          }
          ConvertStringFree(v17);
          if ( v16 )
            return (unsigned int)v16;
        }
        else
        {
          v21 = v27;
          result = ENTRYMGR::AllocDllentrydefn(v27, &v30, v26, 1);
          if ( (int)result < 0 )
            return result;
          LOWORD(v15) = v30;
          *(_WORD *)(*((_QWORD *)v21 + 2) + v30 + 4LL) = (_WORD)a4;
        }
        result = DYN_TYPEROOT::GetDtmbrs(*((DYN_TYPEROOT **)this + 6), &v29);
        if ( !(_DWORD)result )
        {
          v30 = 0;
          result = TYPE_DATA::HfdefnOfIndex((struct DYN_TYPEMEMBERS *)((char *)v29 + 8), a2, &v30);
          if ( (int)result >= 0 )
          {
            *(_WORD *)(v30 + *(_QWORD *)(v22 + 8) + 20LL) = v15;
            return 0;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005f300  push    rbp
0x18005f302  push    rbx
0x18005f303  push    rsi
0x18005f304  push    rdi
0x18005f305  push    r12
0x18005f307  push    r13
0x18005f309  push    r14
0x18005f30b  push    r15
0x18005f30d  mov     rbp, rsp
0x18005f310  sub     rsp, 68h
0x18005f314  xor     r12d, r12d
0x18005f317  mov     rbx, r9
0x18005f31a  mov     [rbp+var_28], r12d
0x18005f31e  mov     rdi, r8
0x18005f321  mov     [rbp+Source], r12
0x18005f325  mov     r13d, edx
0x18005f328  mov     [rbp+var_20], r12
0x18005f32c  mov     r14, rcx
0x18005f32f  mov     [rbp+arg_10], r12d
0x18005f333  mov     [rbp+var_10], r12
0x18005f337  test    r8, r8
0x18005f33a  jnz     short loc_18005F346
0x18005f33c  mov     eax, 80070057h
0x18005f341  jmp     loc_18005F4AE
0x18005f346  mov     rcx, [rcx+30h]; this
0x18005f34a  cmp     [rcx+94h], r12d
0x18005f351  jle     short loc_18005F35D
0x18005f353  mov     eax, 80028029h
0x18005f358  jmp     loc_18005F4AE
0x18005f35d  lea     rdx, [rbp+Source]; struct NAMMGR **
0x18005f361  call    ?GetNamMgr@DYN_TYPEROOT@@QEAAJPEAPEAVNAMMGR@@@Z; DYN_TYPEROOT::GetNamMgr(NAMMGR * *)
0x18005f366  test    eax, eax
0x18005f368  jnz     loc_18005F4AE
0x18005f36e  mov     rcx, [r14+30h]; this
0x18005f372  lea     rdx, [rbp+var_20]; struct ENTRYMGR **
0x18005f376  call    ?GetEntMgr@DYN_TYPEROOT@@QEAAJPEAPEAVENTRYMGR@@@Z; DYN_TYPEROOT::GetEntMgr(ENTRYMGR * *)
0x18005f37b  test    eax, eax
0x18005f37d  jnz     loc_18005F4AE
0x18005f383  mov     rcx, [rbp+Source]; this
0x18005f387  lea     r8, [rbp+var_28]; unsigned int *
0x18005f38b  mov     rdx, rdi; lpWideCharStr
0x18005f38e  call    ?HlnamOfStrW@NAMMGR@@QEAAJPEBGPEAIHPEAHHH@Z; NAMMGR::HlnamOfStrW(ushort const *,uint *,int,int *,int,int)
0x18005f393  test    eax, eax
0x18005f395  jnz     loc_18005F4AE
0x18005f39b  mov     eax, 0FFFF0000h
0x18005f3a0  test    rax, rbx
0x18005f3a3  jz      loc_18005F449
0x18005f3a9  lea     rdx, [rbp+Source]; char **
0x18005f3ad  mov     [rbp+Source], r12
0x18005f3b1  mov     rcx, rbx; lpWideCharStr
0x18005f3b4  call    ?ConvertStringToA@@YAJPEBGPEAPEAD@Z; ConvertStringToA(ushort const *,char * *)
0x18005f3b9  test    eax, eax
0x18005f3bb  jnz     loc_18005F4AE
0x18005f3c1  mov     r15, [rbp+var_20]
0x18005f3c5  lea     rdx, [rbp+arg_10]; unsigned int *
0x18005f3c9  mov     r8d, [rbp+var_28]; unsigned int
0x18005f3cd  mov     rcx, r15; this
0x18005f3d0  xor     r9d, r9d; int
0x18005f3d3  mov     dword ptr [rbp+var_20], r12d
0x18005f3d7  call    ?AllocDllentrydefn@ENTRYMGR@@AEAAJPEAIIH@Z; ENTRYMGR::AllocDllentrydefn(uint *,uint,int)
0x18005f3dc  mov     edi, [rbp+arg_10]
0x18005f3df  mov     ebx, eax
0x18005f3e1  mov     rsi, [rbp+Source]
0x18005f3e5  test    eax, eax
0x18005f3e7  js      short loc_18005F439
0x18005f3e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005f3ed  inc     rax
0x18005f3f0  cmp     [rsi+rax], r12b
0x18005f3f4  jnz     short loc_18005F3ED
0x18005f3f6  lea     r12d, [rax+1]
0x18005f3fa  mov     r8d, r12d; unsigned int
0x18005f3fd  lea     rdx, [rbp+var_20]; unsigned int *
0x18005f401  lea     rcx, [r15+10h]; this
0x18005f405  call    ?AllocChunk2@BLK_MGR@@AEAAJPEAIII@Z; BLK_MGR::AllocChunk2(uint *,uint,uint)
0x18005f40a  mov     ebx, eax
0x18005f40c  test    eax, eax
0x18005f40e  jns     short loc_18005F415
0x18005f410  xor     r12d, r12d
0x18005f413  jmp     short loc_18005F439
0x18005f415  mov     ebx, dword ptr [rbp+var_20]
0x18005f418  mov     r8, rsi; Source
0x18005f41b  mov     ecx, ebx
0x18005f41d  mov     edx, r12d; SizeInBytes
0x18005f420  add     rcx, [r15+10h]; Destination
0x18005f424  call    cs:__imp_strcpy_s
0x18005f42a  mov     rax, [r15+10h]
0x18005f42e  xor     r12d, r12d
0x18005f431  mov     [rdi+rax+4], bx
0x18005f436  mov     ebx, r12d
0x18005f439  mov     rcx, rsi; char *
0x18005f43c  call    ?ConvertStringFree@@YAXPEAD@Z; ConvertStringFree(char *)
0x18005f441  test    ebx, ebx
0x18005f443  jz      short loc_18005F473
0x18005f445  mov     eax, ebx
0x18005f447  jmp     short loc_18005F4AE
0x18005f449  mov     rsi, [rbp+var_20]
0x18005f44d  lea     rdx, [rbp+arg_10]; unsigned int *
0x18005f451  mov     r8d, [rbp+var_28]; unsigned int
0x18005f455  mov     rcx, rsi; this
0x18005f458  mov     r9d, 1; int
0x18005f45e  call    ?AllocDllentrydefn@ENTRYMGR@@AEAAJPEAIIH@Z; ENTRYMGR::AllocDllentrydefn(uint *,uint,int)
0x18005f463  test    eax, eax
0x18005f465  js      short loc_18005F4AE
0x18005f467  mov     edi, [rbp+arg_10]
0x18005f46a  mov     rax, [rsi+10h]
0x18005f46e  mov     [rax+rdi+4], bx
0x18005f473  mov     rcx, [r14+30h]; this
0x18005f477  lea     rdx, [rbp+var_10]; struct DYN_TYPEMEMBERS **
0x18005f47b  call    ?GetDtmbrs@DYN_TYPEROOT@@UEAAJPEAPEAVDYN_TYPEMEMBERS@@@Z; DYN_TYPEROOT::GetDtmbrs(DYN_TYPEMEMBERS * *)
0x18005f480  test    eax, eax
0x18005f482  jnz     short loc_18005F4AE
0x18005f484  mov     r10, [rbp+var_10]
0x18005f488  lea     r8, [rbp+arg_10]; unsigned int *
0x18005f48c  mov     edx, r13d; unsigned int
0x18005f48f  mov     [rbp+arg_10], r12d
0x18005f493  lea     rcx, [r10+8]; this
0x18005f497  call    ?HfdefnOfIndex@TYPE_DATA@@QEAAJIPEAI@Z; TYPE_DATA::HfdefnOfIndex(uint,uint *)
0x18005f49c  test    eax, eax
0x18005f49e  js      short loc_18005F4AE
0x18005f4a0  mov     rax, [r10+8]
0x18005f4a4  mov     ecx, [rbp+arg_10]
0x18005f4a7  mov     [rcx+rax+14h], di
0x18005f4ac  xor     eax, eax
0x18005f4ae  add     rsp, 68h
0x18005f4b2  pop     r15
0x18005f4b4  pop     r14
0x18005f4b6  pop     r13
0x18005f4b8  pop     r12
0x18005f4ba  pop     rdi
0x18005f4bb  pop     rsi
0x18005f4bc  pop     rbx
0x18005f4bd  pop     rbp
0x18005f4be  retn
```
