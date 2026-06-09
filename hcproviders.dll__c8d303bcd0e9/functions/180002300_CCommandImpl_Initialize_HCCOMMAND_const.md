# CCommandImpl::_Initialize(HCCOMMAND const *)

- ea: `0x180002300`
- end: `0x180002505`
- name: `?_Initialize@CCommandImpl@@MEAAJPEBUHCCOMMAND@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(CCommandImpl *__hidden this, const struct HCCOMMAND *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800019f0`
- `0x180009cdc`

## callees

- `0x180002300`
- `0x180002eb0`
- `0x180004a4c`
- `0x180009e16`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002348`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800023da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800023da`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002397`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002397`

## pseudocode

```c
__int64 __fastcall CCommandImpl::_Initialize(CCommandImpl *this, PVOID *a2)
{
  PVOID v2; // r8
  int StringW; // eax
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r14
  int v8; // esi
  char *v10; // rdi
  _WORD *v11; // rax
  unsigned __int64 v12; // rcx
  _WORD *v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r14
  int Error; // eax
  char *Buffer; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a2;
  *((_QWORD *)this + 1) = 0;
  if ( !v2 )
    return 2147500037LL;
  if ( (unsigned __int64)v2 >= 0x10000 )
  {
    Error = _AllocString<CTCoAllocPolicy>(this, a2, v2, (char *)this + 8);
  }
  else
  {
    Buffer = 0;
    StringW = LoadStringW(g_hinst, (UINT)v2, (LPWSTR)&Buffer, 0);
    if ( StringW > 0 )
    {
      v6 = StringW;
      *((_QWORD *)this + 1) = 0;
      v7 = StringW + 1LL;
      if ( v7 >= StringW && is_mul_ok(v7, 2u) )
      {
        v10 = Buffer;
        v11 = CoTaskMemAlloc(2 * v7);
        *((_QWORD *)this + 1) = v11;
        v8 = -2147024882;
        if ( v11 )
          v8 = 0;
        if ( v8 >= 0 )
        {
          if ( !v11 && v7 || v7 > 0x7FFFFFFF )
          {
            *v11 = 0;
          }
          else if ( v6 >= 0x7FFFFFFF )
          {
            if ( v7 )
              *v11 = 0;
          }
          else
          {
            if ( !v10 )
            {
              v10 = byte_18000DBA8;
              v6 = 0;
            }
            if ( v7 )
            {
              v12 = v7;
              v13 = v11;
              v14 = 0;
              while ( v6 && *(_WORD *)v10 )
              {
                *v13 = *(_WORD *)v10;
                v10 += 2;
                ++v13;
                --v6;
                ++v14;
                if ( !--v12 )
                {
                  *(v13 - 1) = 0;
                  goto LABEL_6;
                }
              }
              v15 = v7 - v14;
              *v13 = 0;
              if ( v15 > 1 && 2 * v15 > 2 )
                memset_0(&v11[v14 + 1], 0, 2 * v15 - 2);
            }
          }
        }
      }
      else
      {
        v8 = -2147024362;
      }
      goto LABEL_6;
    }
    Error = ResultFromKnownLastError();
  }
  v8 = Error;
LABEL_6:
  if ( v8 >= 0 )
  {
    *((_QWORD *)this + 2) = DecodePointer(a2[1]);
    *((_DWORD *)this + 6) = *((unsigned __int8 *)a2 + 16);
    *((_DWORD *)this + 7) = *((unsigned __int8 *)a2 + 17);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002300  push    rbp
0x180002302  push    rsi
0x180002303  push    r12
0x180002305  push    r15
0x180002307  sub     rsp, 28h
0x18000230b  mov     r8, [rdx]
0x18000230e  xor     r12d, r12d
0x180002311  mov     [rcx+8], r12
0x180002315  mov     r15, rdx
0x180002318  mov     rbp, rcx
0x18000231b  test    r8, r8
0x18000231e  jz      loc_1800024B6
0x180002324  cmp     r8, 10000h
0x18000232b  jnb     loc_1800024FA
0x180002331  mov     rcx, cs:g_hinst; hInstance
0x180002338  mov     edx, r8d; uID
0x18000233b  lea     r8, [rsp+48h+Buffer]; lpBuffer
0x180002340  mov     [rsp+48h+Buffer], r12
0x180002345  xor     r9d, r9d; cchBufferMax
0x180002348  call    cs:__imp_LoadStringW
0x18000234f  nop     dword ptr [rax+rax+00h]
0x180002354  test    eax, eax
0x180002356  jle     loc_1800024AA
0x18000235c  mov     [rsp+48h+arg_10], rbx
0x180002361  movsxd  rbx, eax
0x180002364  mov     [rsp+48h+var_28], r14
0x180002369  mov     [rsp+48h+arg_18], rdi
0x18000236e  mov     [rbp+8], r12
0x180002372  lea     r14, [rbx+1]
0x180002376  cmp     r14, rbx
0x180002379  jnb     short loc_1800023C5
0x18000237b  mov     esi, 80070216h
0x180002380  mov     r14, [rsp+48h+var_28]
0x180002385  mov     rdi, [rsp+48h+arg_18]
0x18000238a  mov     rbx, [rsp+48h+arg_10]
0x18000238f  test    esi, esi
0x180002391  js      short loc_1800023B7
0x180002393  mov     rcx, [r15+8]; Ptr
0x180002397  call    cs:__imp_DecodePointer
0x18000239e  nop     dword ptr [rax+rax+00h]
0x1800023a3  mov     [rbp+10h], rax
0x1800023a7  movzx   eax, byte ptr [r15+10h]
0x1800023ac  mov     [rbp+18h], eax
0x1800023af  movzx   eax, byte ptr [r15+11h]
0x1800023b4  mov     [rbp+1Ch], eax
0x1800023b7  mov     eax, esi
0x1800023b9  add     rsp, 28h
0x1800023bd  pop     r15
0x1800023bf  pop     r12
0x1800023c1  pop     rsi
0x1800023c2  pop     rbp
0x1800023c3  retn
0x1800023c5  mov     eax, 2
0x1800023ca  mul     r14
0x1800023cd  test    rdx, rdx
0x1800023d0  jnz     short loc_18000237B
0x1800023d2  mov     rdi, [rsp+48h+Buffer]
0x1800023d7  mov     rcx, rax; cb
0x1800023da  call    cs:__imp_CoTaskMemAlloc
0x1800023e1  nop     dword ptr [rax+rax+00h]
0x1800023e6  test    rax, rax
0x1800023e9  mov     [rbp+8], rax
0x1800023ed  mov     esi, 8007000Eh
0x1800023f2  mov     r10, rax
0x1800023f5  cmovnz  esi, r12d
0x1800023f9  test    esi, esi
0x1800023fb  js      short loc_180002380
0x1800023fd  test    rax, rax
0x180002400  jz      loc_1800024C7
0x180002406  cmp     r14, 7FFFFFFFh
0x18000240d  ja      loc_1800024D0
0x180002413  cmp     rbx, 7FFFFFFFh
0x18000241a  jnb     loc_1800024D9
0x180002420  test    rdi, rdi
0x180002423  jz      loc_1800024EB
0x180002429  test    r14, r14
0x18000242c  jz      loc_180002380
0x180002432  mov     rcx, r14
0x180002435  mov     rdx, r10
0x180002438  mov     r9, r12
0x18000243b  nop     dword ptr [rax+rax+00h]
0x180002440  test    rbx, rbx
0x180002443  jz      short loc_180002473
0x180002445  movzx   eax, word ptr [rdi]
0x180002448  test    ax, ax
0x18000244b  jz      short loc_18000246E
0x18000244d  mov     [rdx], ax
0x180002450  add     rdi, 2
0x180002454  add     rdx, 2
0x180002458  dec     rbx
0x18000245b  inc     r9
0x18000245e  sub     rcx, 1
0x180002462  jnz     short loc_180002440
0x180002464  mov     [rdx-2], r12w
0x180002469  jmp     loc_180002380
0x18000246e  test    rcx, rcx
0x180002471  jz      short loc_180002464
0x180002473  sub     r14, r9
0x180002476  mov     [rdx], r12w
0x18000247a  cmp     r14, 1
0x18000247e  jbe     loc_180002380
0x180002484  lea     r8, [r14+r14]
0x180002488  cmp     r8, 2
0x18000248c  jbe     loc_180002380
0x180002492  add     r10, 2
0x180002496  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000249a  xor     edx, edx; Val
0x18000249c  lea     rcx, [r10+r9*2]; void *
0x1800024a0  call    memset_0
0x1800024a5  jmp     loc_180002380
0x1800024aa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800024af  mov     esi, eax
0x1800024b1  jmp     loc_18000238F
0x1800024b6  mov     eax, 80004005h
0x1800024bb  add     rsp, 28h
0x1800024bf  pop     r15
0x1800024c1  pop     r12
0x1800024c3  pop     rsi
0x1800024c4  pop     rbp
0x1800024c5  retn
0x1800024c7  test    r14, r14
0x1800024ca  jz      loc_180002406
0x1800024d0  mov     [rax], r12w
0x1800024d4  jmp     loc_180002380
0x1800024d9  test    r14, r14
0x1800024dc  jz      loc_180002380
0x1800024e2  mov     [rax], r12w
0x1800024e6  jmp     loc_180002380
0x1800024eb  lea     rdi, byte_18000DBA8
0x1800024f2  mov     rbx, r12
0x1800024f5  jmp     loc_180002429
0x1800024fa  lea     r9, [rcx+8]
0x1800024fe  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180002503  jmp     short loc_1800024AF
```
