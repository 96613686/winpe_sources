# SaveLastState(HKEY__ *,ushort const * * const,uint)

- ea: `0x18000fa10`
- end: `0x18000fbd7`
- name: `?SaveLastState@@YAJPEAUHKEY__@@QEAPEBGI@Z`
- size: `455`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 **const, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005b54`

## callees

- `0x180006138`
- `0x18000fa10`
- `0x18000fc58`
- `0x18000fc7c`
- `0x18001e580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000faf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000faf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fb7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fb7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fa42`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fa42`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SaveLastState(HKEY hKey, const unsigned __int16 **const a2, unsigned int a3)
{
  unsigned int v3; // r14d
  HKEY v6; // r13
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  _DWORD *v9; // rdi
  int v10; // ebp
  unsigned int v11; // ebx
  __int64 v12; // r14
  __int64 v13; // rcx
  int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  int v17; // r12d
  const BYTE *v18; // rax
  const BYTE *v19; // rbx
  BYTE *v20; // r15
  __int64 v21; // rbp
  __int64 v22; // rax
  LSTATUS v23; // eax
  int lpData; // [rsp+20h] [rbp-68h]
  LPVOID v26[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v30; // [rsp+A0h] [rbp+18h] BYREF
  const BYTE *v31; // [rsp+A8h] [rbp+20h] BYREF

  v3 = 0;
  v6 = hKey;
  if ( a3 )
  {
    v26[0] = CoTaskMemAlloc(4LL * a3);
    v9 = v26[0];
    if ( v26[0] )
    {
      v10 = 0;
      v11 = 0;
      if ( a3 )
      {
        do
        {
          v12 = v11;
          v13 = -1;
          do
            ++v13;
          while ( a2[v11][v13] );
          v30 = 0;
          v14 = ULongLongToULong(v13 + 1, &v30);
          if ( v14 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, v15, v16, (const char *)(unsigned int)v14, lpData);
          ++v11;
          v10 += v30;
          v9[v12] = v30;
        }
        while ( v11 < a3 );
        v3 = 0;
      }
      v17 = v10 + 1;
      v18 = (const BYTE *)CoTaskMemAlloc(2LL * (unsigned int)(v10 + 1));
      v31 = v18;
      v19 = v18;
      if ( v18 )
      {
        *(_WORD *)&v18[2 * v10] = 0;
        if ( a3 )
        {
          v20 = (BYTE *)v18;
          v21 = 0;
          do
          {
            memcpy_0(v20, a2[v21], 2LL * (unsigned int)v9[v21]);
            v22 = (unsigned int)v9[v21];
            ++v3;
            ++v21;
            v20 += 2 * v22;
          }
          while ( v3 < a3 );
          v6 = hKey;
        }
        v23 = RegSetValueExW(v6, L"CscSuspendedDirs", 0, 7u, v19, 2 * v17);
        v8 = v23;
        if ( v23 )
        {
          if ( v23 > 0 )
            v8 = (unsigned __int16)v23 | 0x80070000;
        }
        else
        {
          v8 = 0;
        }
      }
      else
      {
        v8 = -2147024882;
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v31);
    }
    else
    {
      v8 = -2147024882;
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v26);
  }
  else
  {
    v7 = RegDeleteValueW(hKey, L"CscSuspendedDirs");
    v8 = v7;
    if ( (v7 & 0xFFFFFFFD) != 0 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000fa10  mov     [rsp+arg_8], rdx
0x18000fa15  mov     [rsp+arg_0], rcx
0x18000fa1a  push    rbx
0x18000fa1b  push    rbp
0x18000fa1c  push    rsi
0x18000fa1d  push    rdi
0x18000fa1e  push    r12
0x18000fa20  push    r13
0x18000fa22  push    r14
0x18000fa24  push    r15
0x18000fa26  sub     rsp, 48h
0x18000fa2a  xor     r14d, r14d
0x18000fa2d  mov     esi, r8d
0x18000fa30  mov     r15, rdx
0x18000fa33  mov     r13, rcx
0x18000fa36  test    r8d, r8d
0x18000fa39  jnz     short loc_18000FA6F
0x18000fa3b  lea     rdx, ValueName; "CscSuspendedDirs"
0x18000fa42  call    cs:__imp_RegDeleteValueW
0x18000fa48  mov     ebx, eax
0x18000fa4a  test    eax, 0FFFFFFFDh
0x18000fa4f  jz      short loc_18000FA67
0x18000fa51  test    eax, eax
0x18000fa53  jle     loc_18000FBBB
0x18000fa59  movzx   ebx, ax
0x18000fa5c  or      ebx, 80070000h
0x18000fa62  jmp     loc_18000FBBB
0x18000fa67  mov     ebx, r14d
0x18000fa6a  jmp     loc_18000FBBB
0x18000fa6f  mov     rcx, rsi
0x18000fa72  shl     rcx, 2; cb
0x18000fa76  call    cs:__imp_CoTaskMemAlloc
0x18000fa7c  mov     [rsp+88h+var_58], rax
0x18000fa81  mov     rdi, rax
0x18000fa84  test    rax, rax
0x18000fa87  jz      loc_18000FBAC
0x18000fa8d  mov     ebp, r14d
0x18000fa90  mov     ebx, r14d
0x18000fa93  test    esi, esi
0x18000fa95  jz      short loc_18000FAED
0x18000fa97  xor     r12d, r12d
0x18000fa9a  mov     r14d, ebx
0x18000fa9d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000faa1  mov     rax, [r15+r14*8]
0x18000faa5  inc     rcx
0x18000faa8  cmp     [rax+rcx*2], r12w
0x18000faad  jnz     short loc_18000FAA5
0x18000faaf  inc     rcx; unsigned __int64
0x18000fab2  mov     [rsp+88h+arg_10], r12d
0x18000faba  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x18000fac2  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000fac7  mov     rcx, [rsp+88h]; this
0x18000facf  test    eax, eax
0x18000fad1  js      loc_18000FBCE
0x18000fad7  mov     eax, [rsp+88h+arg_10]
0x18000fade  inc     ebx
0x18000fae0  add     ebp, eax
0x18000fae2  mov     [rdi+r14*4], eax
0x18000fae6  cmp     ebx, esi
0x18000fae8  jb      short loc_18000FA9A
0x18000faea  xor     r14d, r14d
0x18000faed  lea     r12d, [rbp+1]
0x18000faf1  mov     ecx, r12d
0x18000faf4  add     rcx, rcx; cb
0x18000faf7  call    cs:__imp_CoTaskMemAlloc
0x18000fafd  mov     [rsp+88h+arg_18], rax
0x18000fb05  mov     rbx, rax
0x18000fb08  test    rax, rax
0x18000fb0b  jz      loc_18000FB98
0x18000fb11  mov     ecx, ebp
0x18000fb13  mov     [rax+rcx*2], r14w
0x18000fb18  test    esi, esi
0x18000fb1a  jz      short loc_18000FB5A
0x18000fb1c  mov     r13, [rsp+88h+arg_8]
0x18000fb24  mov     r15, rax
0x18000fb27  xor     ebp, ebp
0x18000fb29  mov     r8d, [rdi+rbp*4]
0x18000fb2d  mov     rcx, r15; void *
0x18000fb30  mov     rdx, [r13+rbp*8+0]; Src
0x18000fb35  add     r8, r8; Size
0x18000fb38  call    memcpy_0
0x18000fb3d  mov     eax, [rdi+rbp*4]
0x18000fb40  inc     r14d
0x18000fb43  inc     rbp
0x18000fb46  lea     r15, [r15+rax*2]
0x18000fb4a  cmp     r14d, esi
0x18000fb4d  jb      short loc_18000FB29
0x18000fb4f  mov     r13, [rsp+88h+arg_0]
0x18000fb57  xor     r14d, r14d
0x18000fb5a  lea     eax, [r12+r12]
0x18000fb5e  mov     r9d, 7; dwType
0x18000fb64  mov     [rsp+88h+cbData], eax; cbData
0x18000fb68  lea     rdx, ValueName; "CscSuspendedDirs"
0x18000fb6f  xor     r8d, r8d; Reserved
0x18000fb72  mov     [rsp+88h+lpData], rbx; lpData
0x18000fb77  mov     rcx, r13; hKey
0x18000fb7a  call    cs:__imp_RegSetValueExW
0x18000fb80  mov     ebx, eax
0x18000fb82  test    eax, eax
0x18000fb84  jnz     short loc_18000FB8B
0x18000fb86  mov     ebx, r14d
0x18000fb89  jmp     short loc_18000FB9D
0x18000fb8b  jle     short loc_18000FB9D
0x18000fb8d  movzx   ebx, ax
0x18000fb90  or      ebx, 80070000h
0x18000fb96  jmp     short loc_18000FB9D
0x18000fb98  mov     ebx, 8007000Eh
0x18000fb9d  lea     rcx, [rsp+88h+arg_18]
0x18000fba5  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000fbaa  jmp     short loc_18000FBB1
0x18000fbac  mov     ebx, 8007000Eh
0x18000fbb1  lea     rcx, [rsp+88h+var_58]
0x18000fbb6  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000fbbb  mov     eax, ebx
0x18000fbbd  add     rsp, 48h
0x18000fbc1  pop     r15
0x18000fbc3  pop     r14
0x18000fbc5  pop     r13
0x18000fbc7  pop     r12
0x18000fbc9  pop     rdi
0x18000fbca  pop     rsi
0x18000fbcb  pop     rbp
0x18000fbcc  pop     rbx
0x18000fbcd  retn
0x18000fbce  mov     r9d, eax; char *
0x18000fbd1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
