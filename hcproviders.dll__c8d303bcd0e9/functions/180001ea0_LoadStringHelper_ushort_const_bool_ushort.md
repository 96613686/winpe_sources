# LoadStringHelper(ushort const *,bool,ushort * *)

- ea: `0x180001ea0`
- end: `0x180002063`
- name: `?LoadStringHelper@@YAJPEBG_NPEAPEAG@Z`
- size: `451`
- prototype: `__int64 __fastcall(UINT uID, bool, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001490`
- `0x1800019f0`
- `0x180009a10`

## callees

- `0x180001ea0`
- `0x180002eb0`
- `0x180004a4c`
- `0x180009e16`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001edb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001edb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001f40`

## pseudocode

```c
__int64 __fastcall LoadStringHelper(char *uID, __int64 a2, unsigned __int16 **a3)
{
  int StringW; // eax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  unsigned int v7; // esi
  __int64 result; // rax
  char *v9; // rdi
  unsigned __int16 *v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int16 *v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // r14
  char *Buffer; // [rsp+40h] [rbp+8h] BYREF

  *a3 = 0;
  if ( uID )
  {
    if ( (unsigned __int64)uID >= 0x10000 )
    {
      return _AllocString<CTCoAllocPolicy>((__int64)uID, a2, uID, a3);
    }
    else
    {
      Buffer = 0;
      StringW = LoadStringW(g_hinst, (UINT)uID, (LPWSTR)&Buffer, 0);
      if ( StringW > 0 )
      {
        v5 = StringW;
        *a3 = 0;
        v6 = StringW + 1LL;
        if ( v6 >= StringW && is_mul_ok(v6, 2u) )
        {
          v9 = Buffer;
          v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
          *a3 = v10;
          v7 = -2147024882;
          if ( v10 )
            v7 = 0;
          if ( (v7 & 0x80000000) == 0 )
          {
            if ( !v10 && v6 || v6 > 0x7FFFFFFF )
              goto LABEL_32;
            if ( v5 < 0x7FFFFFFF )
            {
              if ( !v9 )
              {
                v9 = byte_18000DBA8;
                v5 = 0;
              }
              if ( v6 )
              {
                v11 = v6;
                v12 = v10;
                v13 = 0;
                while ( v5 && *(_WORD *)v9 )
                {
                  *v12 = *(_WORD *)v9;
                  v9 += 2;
                  ++v12;
                  --v5;
                  ++v13;
                  if ( !--v11 )
                  {
                    *(v12 - 1) = 0;
                    return v7;
                  }
                }
                v14 = v6 - v13;
                *v12 = 0;
                if ( v14 > 1 && 2 * v14 > 2 )
                  memset_0(&v10[v13 + 1], 0, 2 * v14 - 2);
              }
              return v7;
            }
            if ( v6 )
LABEL_32:
              *v10 = 0;
          }
        }
        else
        {
          return (unsigned int)-2147024362;
        }
        return v7;
      }
      return ResultFromKnownLastError();
    }
  }
  else
  {
    result = 0;
    if ( !(_BYTE)a2 )
      return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001ea0  push    rbp
0x180001ea2  push    rsi
0x180001ea3  sub     rsp, 28h
0x180001ea7  xor     ebp, ebp
0x180001ea9  mov     rsi, r8
0x180001eac  mov     [r8], rbp
0x180001eaf  test    rcx, rcx
0x180001eb2  jz      loc_180002008
0x180001eb8  cmp     rcx, 10000h
0x180001ebf  jnb     loc_180002053
0x180001ec5  mov     edx, ecx; uID
0x180001ec7  mov     [rsp+38h+Buffer], rbp
0x180001ecc  mov     rcx, cs:g_hinst; hInstance
0x180001ed3  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x180001ed8  xor     r9d, r9d; cchBufferMax
0x180001edb  call    cs:__imp_LoadStringW
0x180001ee2  nop     dword ptr [rax+rax+00h]
0x180001ee7  test    eax, eax
0x180001ee9  jle     loc_18000201C
0x180001eef  mov     [rsp+38h+arg_8], rbx
0x180001ef4  movsxd  rbx, eax
0x180001ef7  mov     [rsp+38h+var_18], r14
0x180001efc  mov     [rsp+38h+arg_18], rdi
0x180001f01  mov     [rsi], rbp
0x180001f04  lea     r14, [rbx+1]
0x180001f08  cmp     r14, rbx
0x180001f0b  jnb     short loc_180001F2B
0x180001f0d  mov     esi, 80070216h
0x180001f12  mov     r14, [rsp+38h+var_18]
0x180001f17  mov     eax, esi
0x180001f19  mov     rdi, [rsp+38h+arg_18]
0x180001f1e  mov     rbx, [rsp+38h+arg_8]
0x180001f23  add     rsp, 28h
0x180001f27  pop     rsi
0x180001f28  pop     rbp
0x180001f29  retn
0x180001f2b  mov     eax, 2
0x180001f30  mul     r14
0x180001f33  test    rdx, rdx
0x180001f36  jnz     short loc_180001F0D
0x180001f38  mov     rdi, [rsp+38h+Buffer]
0x180001f3d  mov     rcx, rax; cb
0x180001f40  call    cs:__imp_CoTaskMemAlloc
0x180001f47  nop     dword ptr [rax+rax+00h]
0x180001f4c  mov     [rsi], rax
0x180001f4f  test    rax, rax
0x180001f52  mov     esi, 8007000Eh
0x180001f57  mov     r10, rax
0x180001f5a  cmovnz  esi, ebp
0x180001f5d  test    esi, esi
0x180001f5f  js      short loc_180001F12
0x180001f61  test    rax, rax
0x180001f64  jz      loc_180002029
0x180001f6a  cmp     r14, 7FFFFFFFh
0x180001f71  ja      loc_18000203C
0x180001f77  cmp     rbx, 7FFFFFFFh
0x180001f7e  jnb     loc_180002033
0x180001f84  test    rdi, rdi
0x180001f87  jz      loc_180002044
0x180001f8d  test    r14, r14
0x180001f90  jz      short loc_180001F12
0x180001f92  mov     rcx, r14
0x180001f95  mov     rdx, r10
0x180001f98  mov     r9, rbp
0x180001f9b  nop     dword ptr [rax+rax+00h]
0x180001fa0  test    rbx, rbx
0x180001fa3  jz      short loc_180001FD2
0x180001fa5  movzx   eax, word ptr [rdi]
0x180001fa8  test    ax, ax
0x180001fab  jz      short loc_180001FCD
0x180001fad  mov     [rdx], ax
0x180001fb0  add     rdi, 2
0x180001fb4  add     rdx, 2
0x180001fb8  dec     rbx
0x180001fbb  inc     r9
0x180001fbe  sub     rcx, 1
0x180001fc2  jnz     short loc_180001FA0
0x180001fc4  mov     [rdx-2], bp
0x180001fc8  jmp     loc_180001F12
0x180001fcd  test    rcx, rcx
0x180001fd0  jz      short loc_180001FC4
0x180001fd2  sub     r14, r9
0x180001fd5  mov     [rdx], bp
0x180001fd8  cmp     r14, 1
0x180001fdc  jbe     loc_180001F12
0x180001fe2  lea     r8, [r14+r14]
0x180001fe6  cmp     r8, 2
0x180001fea  jbe     loc_180001F12
0x180001ff0  add     r10, 2
0x180001ff4  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180001ff8  xor     edx, edx; Val
0x180001ffa  lea     rcx, [r10+r9*2]; void *
0x180001ffe  call    memset_0
0x180002003  jmp     loc_180001F12
0x180002008  test    dl, dl
0x18000200a  mov     eax, ebp
0x18000200c  mov     ecx, 80004005h
0x180002011  cmovz   eax, ecx
0x180002014  add     rsp, 28h
0x180002018  pop     rsi
0x180002019  pop     rbp
0x18000201a  retn
0x18000201c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180002021  add     rsp, 28h
0x180002025  pop     rsi
0x180002026  pop     rbp
0x180002027  retn
0x180002029  test    r14, r14
0x18000202c  jnz     short loc_18000203C
0x18000202e  jmp     loc_180001F6A
0x180002033  test    r14, r14
0x180002036  jz      loc_180001F12
0x18000203c  mov     [rax], bp
0x18000203f  jmp     loc_180001F12
0x180002044  lea     rdi, byte_18000DBA8
0x18000204b  mov     rbx, rbp
0x18000204e  jmp     loc_180001F8D
0x180002053  mov     r9, rsi
0x180002056  mov     r8, rcx
0x180002059  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000205e  jmp     loc_180001F23
```
