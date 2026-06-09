# RetrievePropertyName(IMDCOM *,ulong,STRU *)

- ea: `0x18000f730`
- end: `0x18000f903`
- name: `?RetrievePropertyName@@YAJPEAUIMDCOM@@KPEAVSTRU@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(struct IMDCOM *, unsigned int, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000238c`

## callees

- `0x18000f730`
- `0x18000fb1e`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000f8d9`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000f8d9`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f842`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f842`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f8cf`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f8cf`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000f77c`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000f77c`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8b5`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8b5`

## pseudocode

```c
__int64 __fastcall RetrievePropertyName(struct IMDCOM *a1, int a2, struct STRU *a3)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(struct IMDCOM *, _QWORD, const wchar_t *, __int128 *, unsigned int *); // rax
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+58h] [rbp-A8h]
  _BYTE v16[32]; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v17; // [rsp+80h] [rbp-80h]
  unsigned int v18; // [rsp+88h] [rbp-78h]
  __int16 v19; // [rsp+8Ch] [rbp-74h]
  _BYTE v20[64]; // [rsp+90h] [rbp-70h] BYREF
  char v21; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v22[527]; // [rsp+D1h] [rbp-2Fh] BYREF

  v15 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  STRU::STRU((STRU *)v20);
  memset_0(v22, 0, 0x207u);
  v21 = 0;
  v17 = (const unsigned __int16 *)&v21;
  v18 = 520;
  v19 = 256;
  if ( !a1 || !a3 )
  {
    v9 = -2147024809;
    goto LABEL_15;
  }
  LODWORD(v13) = a2;
  *((_QWORD *)&v14 + 1) = &v21;
  v6 = *(_QWORD *)a1;
  *(_QWORD *)((char *)&v13 + 4) = 0;
  HIDWORD(v13) = 2;
  v7 = *(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, const wchar_t *, __int128 *, unsigned int *))(v6 + 168);
  LODWORD(v14) = 260;
  LODWORD(v15) = 0;
  v8 = v7(a1, 0, L"/Schema/Properties/Names", &v13, &v12);
  v9 = v8;
  if ( v8 >= 0 )
  {
LABEL_10:
    v17[((unsigned __int64)v18 >> 1) - 1] = 0;
    v10 = STRU::Copy(a3, v17);
    goto LABEL_12;
  }
  if ( v8 != -2147024893 && v8 != -2146646015 )
  {
    if ( v8 != -2147024774 )
      goto LABEL_15;
    if ( !BUFFER::Resize((BUFFER *)v16, v12) )
    {
      v9 = -2147024882;
      goto LABEL_15;
    }
    *((_QWORD *)&v14 + 1) = v17;
    LODWORD(v14) = v12;
    v9 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, const wchar_t *, __int128 *, unsigned int *))(*(_QWORD *)a1 + 168LL))(
           a1,
           0,
           L"/Schema/Properties/Names",
           &v13,
           &v12);
    if ( v9 < 0 )
      goto LABEL_15;
    goto LABEL_10;
  }
  v10 = STRU::Copy(a3, L"-");
LABEL_12:
  v9 = v10;
  if ( v10 >= 0 )
    v9 = 0;
LABEL_15:
  BUFFER::~BUFFER((BUFFER *)v16);
  STRU::~STRU((STRU *)v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f730  mov     [rsp-8+arg_18], rbx
0x18000f735  push    rbp
0x18000f736  push    rsi
0x18000f737  push    rdi
0x18000f738  lea     rbp, [rsp-1F0h]
0x18000f740  sub     rsp, 2F0h
0x18000f747  mov     rax, cs:__security_cookie
0x18000f74e  xor     rax, rsp
0x18000f751  mov     [rbp+200h+var_20], rax
0x18000f758  xorps   xmm0, xmm0
0x18000f75b  xor     eax, eax
0x18000f75d  mov     rsi, rcx
0x18000f760  mov     [rsp+300h+var_2A8], rax
0x18000f765  lea     rcx, [rbp+200h+var_270]
0x18000f769  mov     [rsp+300h+var_2D0], eax
0x18000f76d  movups  [rsp+300h+var_2C8], xmm0
0x18000f772  mov     rdi, r8
0x18000f775  mov     ebx, edx
0x18000f777  movups  [rsp+300h+var_2B8], xmm0
0x18000f77c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000f782  xor     edx, edx; Val
0x18000f784  lea     rcx, [rbp+200h+var_22F]; void *
0x18000f788  mov     r8d, 207h; Size
0x18000f78e  call    memset_0
0x18000f793  mov     [rbp+200h+var_230], 0
0x18000f797  lea     rax, [rbp+200h+var_230]
0x18000f79b  mov     [rbp+200h+var_280], rax
0x18000f79f  mov     [rbp+200h+var_278], 208h
0x18000f7a6  mov     [rbp+200h+var_274], 100h
0x18000f7ac  test    rsi, rsi
0x18000f7af  jz      loc_18000F8C5
0x18000f7b5  test    rdi, rdi
0x18000f7b8  jz      loc_18000F8C5
0x18000f7be  lea     rax, [rbp+200h+var_230]
0x18000f7c2  mov     dword ptr [rsp+300h+var_2C8], ebx
0x18000f7c6  mov     qword ptr [rsp+300h+var_2B8+8], rax
0x18000f7cb  lea     rcx, [rsp+300h+var_2D0]
0x18000f7d0  mov     rax, [rsi]
0x18000f7d3  lea     r9, [rsp+300h+var_2C8]
0x18000f7d8  mov     [rsp+300h+var_2E0], rcx
0x18000f7dd  lea     r8, aSchemaProperti_0; "/Schema/Properties/Names"
0x18000f7e4  xor     edx, edx
0x18000f7e6  mov     qword ptr [rsp+300h+var_2C8+4], 0
0x18000f7ef  mov     rcx, rsi
0x18000f7f2  mov     dword ptr [rsp+300h+var_2C8+0Ch], 2
0x18000f7fa  mov     rax, [rax+0A8h]
0x18000f801  mov     dword ptr [rsp+300h+var_2B8], 104h
0x18000f809  mov     dword ptr [rsp+300h+var_2A8], 0
0x18000f811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f816  mov     ebx, eax
0x18000f818  test    eax, eax
0x18000f81a  jns     short loc_18000F894
0x18000f81c  cmp     eax, 80070003h
0x18000f821  jz      loc_18000F8AB
0x18000f827  cmp     eax, 800CC801h
0x18000f82c  jz      short loc_18000F8AB
0x18000f82e  cmp     eax, 8007007Ah
0x18000f833  jnz     loc_18000F8CA
0x18000f839  mov     edx, [rsp+300h+var_2D0]
0x18000f83d  lea     rcx, [rsp+300h+var_2A0]
0x18000f842  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000f848  test    al, al
0x18000f84a  jnz     short loc_18000F853
0x18000f84c  mov     ebx, 8007000Eh
0x18000f851  jmp     short loc_18000F8CA
0x18000f853  mov     rax, [rbp+200h+var_280]
0x18000f857  lea     rcx, [rsp+300h+var_2D0]
0x18000f85c  mov     qword ptr [rsp+300h+var_2B8+8], rax
0x18000f861  lea     r9, [rsp+300h+var_2C8]
0x18000f866  mov     eax, [rsp+300h+var_2D0]
0x18000f86a  lea     r8, aSchemaProperti_0; "/Schema/Properties/Names"
0x18000f871  mov     dword ptr [rsp+300h+var_2B8], eax
0x18000f875  xor     edx, edx
0x18000f877  mov     rax, [rsi]
0x18000f87a  mov     [rsp+300h+var_2E0], rcx
0x18000f87f  mov     rcx, rsi
0x18000f882  mov     rax, [rax+0A8h]
0x18000f889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88e  mov     ebx, eax
0x18000f890  test    eax, eax
0x18000f892  js      short loc_18000F8CA
0x18000f894  mov     edx, [rbp+200h+var_278]
0x18000f897  mov     rax, [rbp+200h+var_280]
0x18000f89b  shr     rdx, 1
0x18000f89e  xor     ecx, ecx
0x18000f8a0  mov     [rax+rdx*2-2], cx
0x18000f8a5  mov     rdx, [rbp+200h+var_280]
0x18000f8a9  jmp     short loc_18000F8B2
0x18000f8ab  lea     rdx, asc_180012680; "-"
0x18000f8b2  mov     rcx, rdi
0x18000f8b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f8bb  mov     ebx, eax
0x18000f8bd  test    eax, eax
0x18000f8bf  js      short loc_18000F8CA
0x18000f8c1  xor     ebx, ebx
0x18000f8c3  jmp     short loc_18000F8CA
0x18000f8c5  mov     ebx, 80070057h
0x18000f8ca  lea     rcx, [rsp+300h+var_2A0]
0x18000f8cf  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000f8d5  lea     rcx, [rbp+200h+var_270]
0x18000f8d9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f8df  mov     eax, ebx
0x18000f8e1  mov     rcx, [rbp+200h+var_20]
0x18000f8e8  xor     rcx, rsp; StackCookie
0x18000f8eb  call    __security_check_cookie
0x18000f8f0  mov     rbx, [rsp+300h+arg_18]
0x18000f8f8  add     rsp, 2F0h
0x18000f8ff  pop     rdi
0x18000f900  pop     rsi
0x18000f901  pop     rbp
0x18000f902  retn
```
