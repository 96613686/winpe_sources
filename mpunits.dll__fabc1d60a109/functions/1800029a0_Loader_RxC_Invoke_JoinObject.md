# Loader_RxC_Invoke_JoinObject

- ea: `0x1800029a0`
- end: `0x180002c75`
- name: `Loader_RxC_Invoke_JoinObject`
- size: `725`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029a0`
- `0x180006ef8`
- `0x180007c80`
- `0x180008ea0`
- `0x180008f20`
- `0x180030a30`
- `0x1800396fc`
- `0x18003cb20`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180002bcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180002bcd`

## string_xrefs

- `0x180002bc2`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Loader_RxC_Invoke_JoinObject(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  __int64 v7; // r14
  __int64 *v8; // rdi
  __int64 *v9; // r15
  char v11; // bl
  bool v12; // si
  char v13; // al
  unsigned int v14; // ebx
  __int64 result; // rax
  __int64 v16; // rcx
  const wchar_t *v17; // rcx
  __int64 v18; // r13
  __int64 v19; // rsi
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  HMODULE ModuleHandleA; // rax
  __int128 v27; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v28; // [rsp+98h] [rbp+50h] BYREF

  v7 = a7;
  v8 = 0;
  v9 = 0;
  v28 = 0;
  *(_QWORD *)&v27 = 0;
  v11 = 1;
  v12 = *(_BYTE *)(a7 + 145) && *(_BYTE *)(a7 + 144);
  if ( !*(_BYTE *)(a7 + 148) || !*(_BYTE *)(a7 + 147) )
    v11 = 0;
  v13 = *(_BYTE *)(a7 + 104);
  if ( *(_BYTE *)(a7 + 88) )
  {
    if ( v13 )
    {
      v14 = 4;
      result = MI_ReportErrorDetails_MutuallyExclusiveParameters(L"UpstreamPipe", L"Left");
      goto LABEL_34;
    }
    v16 = *(_QWORD *)(a7 + 80);
  }
  else
  {
    if ( !v13 )
    {
      v17 = L"UpstreamPipe";
LABEL_14:
      v14 = 4;
      result = MI_ReportErrorDetails_MandatoryParameterMissing((__int64)v17);
      goto LABEL_34;
    }
    v16 = *(_QWORD *)(a7 + 96);
  }
  v18 = ((__int64 (__fastcall *)(__int64))Observable_FromInstance)(v16);
  if ( !*(_BYTE *)(v7 + 120) )
  {
    v17 = L"Right";
    goto LABEL_14;
  }
  if ( !*(_BYTE *)(v7 + 136) )
  {
    result = MI_ReportErrorDetails_MandatoryParameterMissing((__int64)L"ScriptBlock");
LABEL_20:
    v14 = 4;
    goto LABEL_34;
  }
  if ( v12 )
  {
    if ( v11 )
    {
      result = MI_ReportErrorDetails_MutuallyExclusiveParameters(L"UseLatestRight", L"ByPosition");
      goto LABEL_20;
    }
    v19 = *(_QWORD *)(v7 + 112);
    v20 = ((__int64 (__fastcall *)(_QWORD))Delegate_FromInstance)(*(_QWORD *)(v7 + 128));
    v21 = ((__int64 (__fastcall *)(__int64))Observable_FromInstance)(v19);
    result = RxcLopsidedCombineLatest(v18, v21, v20, &v28);
  }
  else
  {
    if ( !v11 )
    {
      v27 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v27 = Intlstr_GetString_LoadString(ModuleHandleA, 2046);
      BYTE8(v27) = 0;
      v14 = 4;
      result = MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      goto LABEL_34;
    }
    v22 = *(_QWORD *)(v7 + 112);
    v23 = ((__int64 (__fastcall *)(_QWORD))Delegate_FromInstance)(*(_QWORD *)(v7 + 128));
    v24 = ((__int64 (__fastcall *)(__int64))Observable_FromInstance)(v22);
    result = RxcZip(v18, v24, v23, &v28);
  }
  v8 = v28;
  v14 = result;
  if ( !(_DWORD)result )
  {
    result = RxcUnravel(v28, &v27);
    v9 = (__int64 *)v27;
    v14 = result;
    if ( !(_DWORD)result )
    {
      v25 = *(_QWORD *)v7;
      a7 = v27;
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64, int))(v25 + 80))(
                 v7,
                 0,
                 &a7,
                 15,
                 0x40000000);
      v14 = result;
      if ( !(_DWORD)result )
      {
        if ( a2 )
        {
          result = *a2;
          if ( *a2 )
          {
            result = (*(__int64 (__fastcall **)(__int64 *, __int64))(result + 8))(a2, v7);
            v14 = result;
            goto LABEL_34;
          }
        }
        goto LABEL_20;
      }
    }
  }
LABEL_34:
  if ( v8 )
  {
    result = *v8;
    if ( *v8 )
      result = (*(__int64 (__fastcall **)(__int64 *))(result + 16))(v8);
  }
  if ( v9 )
  {
    result = *v9;
    if ( *v9 )
      result = (*(__int64 (__fastcall **)(__int64 *))(result + 16))(v9);
  }
  if ( a2 )
  {
    result = *a2;
    if ( *a2 )
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD))result)(a2, v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800029a0  push    rbp
0x1800029a2  push    rbx
0x1800029a3  push    rsi
0x1800029a4  push    rdi
0x1800029a5  push    r12
0x1800029a7  push    r13
0x1800029a9  push    r14
0x1800029ab  push    r15
0x1800029ad  mov     rbp, rsp
0x1800029b0  sub     rsp, 48h
0x1800029b4  mov     r14, [rbp+arg_30]
0x1800029b8  xor     edi, edi
0x1800029ba  xor     r15d, r15d
0x1800029bd  mov     [rbp+arg_8], rdi
0x1800029c1  mov     r12, rdx
0x1800029c4  mov     qword ptr [rbp+var_18], r15
0x1800029c8  mov     bl, 1
0x1800029ca  cmp     [r14+91h], dil
0x1800029d1  jz      short loc_1800029E1
0x1800029d3  cmp     [r14+90h], dil
0x1800029da  jz      short loc_1800029E1
0x1800029dc  mov     sil, bl
0x1800029df  jmp     short loc_1800029E4
0x1800029e1  xor     sil, sil
0x1800029e4  cmp     [r14+94h], dil
0x1800029eb  jz      short loc_1800029F6
0x1800029ed  cmp     [r14+93h], dil
0x1800029f4  jnz     short loc_1800029F8
0x1800029f6  xor     bl, bl
0x1800029f8  mov     al, [r14+68h]
0x1800029fc  cmp     [r14+58h], dil
0x180002a00  jz      short loc_180002A29
0x180002a02  test    al, al
0x180002a04  jz      short loc_180002A23
0x180002a06  lea     rdx, aLeft_0; "Left"
0x180002a0d  mov     ebx, 4
0x180002a12  lea     rcx, aUpstreampipe_0; "UpstreamPipe"
0x180002a19  call    MI_ReportErrorDetails_MutuallyExclusiveParameters
0x180002a1e  jmp     loc_180002C17
0x180002a23  mov     rcx, [r14+50h]
0x180002a27  jmp     short loc_180002A47
0x180002a29  test    al, al
0x180002a2b  jnz     short loc_180002A43
0x180002a2d  lea     rcx, aUpstreampipe_0; "UpstreamPipe"
0x180002a34  mov     ebx, 4
0x180002a39  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x180002a3e  jmp     loc_180002C17
0x180002a43  mov     rcx, [r14+60h]
0x180002a47  mov     rax, cs:off_180047B90
0x180002a4e  mov     rax, [rax+8]
0x180002a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a57  mov     r13, rax
0x180002a5a  cmp     [r14+78h], dil
0x180002a5e  jnz     short loc_180002A69
0x180002a60  lea     rcx, aRight_0; "Right"
0x180002a67  jmp     short loc_180002A34
0x180002a69  cmp     [r14+88h], dil
0x180002a70  jnz     short loc_180002A88
0x180002a72  lea     rcx, aScriptblock; "ScriptBlock"
0x180002a79  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x180002a7e  mov     ebx, 4
0x180002a83  jmp     loc_180002C17
0x180002a88  test    sil, sil
0x180002a8b  jz      short loc_180002AF1
0x180002a8d  test    bl, bl
0x180002a8f  jz      short loc_180002AA6
0x180002a91  lea     rdx, aByposition_0; "ByPosition"
0x180002a98  lea     rcx, aUselatestright_0; "UseLatestRight"
0x180002a9f  call    MI_ReportErrorDetails_MutuallyExclusiveParameters
0x180002aa4  jmp     short loc_180002A7E
0x180002aa6  mov     rax, cs:off_180047B98
0x180002aad  mov     rcx, [r14+80h]
0x180002ab4  mov     rsi, [r14+70h]
0x180002ab8  mov     rdx, [rax+8]
0x180002abc  mov     rax, cs:off_180047B90
0x180002ac3  mov     rdi, [rax+8]
0x180002ac7  mov     rax, rdx
0x180002aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acf  mov     rbx, rax
0x180002ad2  mov     rcx, rsi
0x180002ad5  mov     rax, rdi
0x180002ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002add  mov     rdx, rax
0x180002ae0  lea     r9, [rbp+arg_8]
0x180002ae4  mov     r8, rbx
0x180002ae7  mov     rcx, r13
0x180002aea  call    RxcLopsidedCombineLatest
0x180002aef  jmp     short loc_180002B3F
0x180002af1  test    bl, bl
0x180002af3  jz      loc_180002BBF
0x180002af9  mov     rax, cs:off_180047B98
0x180002b00  mov     rdx, cs:off_180047B90
0x180002b07  mov     rcx, [r14+80h]
0x180002b0e  mov     rsi, [r14+70h]
0x180002b12  mov     rax, [rax+8]
0x180002b16  mov     rdi, [rdx+8]
0x180002b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1f  mov     rbx, rax
0x180002b22  mov     rcx, rsi
0x180002b25  mov     rax, rdi
0x180002b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b2d  mov     rdx, rax
0x180002b30  lea     r9, [rbp+arg_8]
0x180002b34  mov     r8, rbx
0x180002b37  mov     rcx, r13
0x180002b3a  call    RxcZip
0x180002b3f  mov     rdi, [rbp+arg_8]
0x180002b43  mov     ebx, eax
0x180002b45  test    eax, eax
0x180002b47  jnz     loc_180002C17
0x180002b4d  lea     rdx, [rbp+var_18]
0x180002b51  mov     rcx, rdi
0x180002b54  call    RxcUnravel
0x180002b59  mov     r15, qword ptr [rbp+var_18]
0x180002b5d  mov     ebx, eax
0x180002b5f  test    eax, eax
0x180002b61  jnz     loc_180002C17
0x180002b67  mov     rax, [r14]
0x180002b6a  lea     r9d, [rbx+0Fh]
0x180002b6e  mov     [rbp+arg_30], r15
0x180002b72  lea     r8, [rbp+arg_30]
0x180002b76  xor     edx, edx
0x180002b78  mov     dword ptr [rsp+48h+var_28], 40000000h
0x180002b80  mov     rcx, r14
0x180002b83  mov     rax, [rax+50h]
0x180002b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b8c  mov     ebx, eax
0x180002b8e  test    eax, eax
0x180002b90  jnz     loc_180002C17
0x180002b96  test    r12, r12
0x180002b99  jz      loc_180002A7E
0x180002b9f  mov     rax, [r12]
0x180002ba3  test    rax, rax
0x180002ba6  jz      loc_180002A7E
0x180002bac  mov     rax, [rax+8]
0x180002bb0  mov     rdx, r14
0x180002bb3  mov     rcx, r12
0x180002bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bbb  mov     ebx, eax
0x180002bbd  jmp     short loc_180002C17
0x180002bbf  xorps   xmm0, xmm0
0x180002bc2  lea     rcx, ModuleName; "mpunits.dll"
0x180002bc9  movups  [rbp+var_18], xmm0
0x180002bcd  call    cs:__imp_GetModuleHandleA
0x180002bd3  mov     rcx, rax
0x180002bd6  mov     edx, 7FEh
0x180002bdb  call    _Intlstr_GetString_LoadString
0x180002be0  mov     qword ptr [rbp+var_18], rax
0x180002be4  lea     r9, [rbp+var_18]
0x180002be8  mov     byte ptr [rbp+var_18+8], dil
0x180002bec  lea     rdx, aMi; "MI"
0x180002bf3  movaps  xmm0, [rbp+var_18]
0x180002bf7  mov     r8d, 5
0x180002bfd  mov     [rsp+48h+var_20], rdi; __int64
0x180002c02  movdqa  [rbp+var_18], xmm0
0x180002c07  mov     [rsp+48h+var_28], rdi; __int64
0x180002c0c  lea     ebx, [r8-1]
0x180002c10  mov     ecx, ebx; int
0x180002c12  call    MI_ReportErrorDetails_ForCustomError
0x180002c17  test    rdi, rdi
0x180002c1a  jz      short loc_180002C30
0x180002c1c  mov     rax, [rdi]
0x180002c1f  test    rax, rax
0x180002c22  jz      short loc_180002C30
0x180002c24  mov     rax, [rax+10h]
0x180002c28  mov     rcx, rdi
0x180002c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c30  test    r15, r15
0x180002c33  jz      short loc_180002C49
0x180002c35  mov     rax, [r15]
0x180002c38  test    rax, rax
0x180002c3b  jz      short loc_180002C49
0x180002c3d  mov     rax, [rax+10h]
0x180002c41  mov     rcx, r15
0x180002c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c49  test    r12, r12
0x180002c4c  jz      short loc_180002C64
0x180002c4e  mov     rax, [r12]
0x180002c52  test    rax, rax
0x180002c55  jz      short loc_180002C64
0x180002c57  mov     rax, [rax]
0x180002c5a  mov     edx, ebx
0x180002c5c  mov     rcx, r12
0x180002c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c64  add     rsp, 48h
0x180002c68  pop     r15
0x180002c6a  pop     r14
0x180002c6c  pop     r13
0x180002c6e  pop     r12
0x180002c70  pop     rdi
0x180002c71  pop     rsi
0x180002c72  pop     rbx
0x180002c73  pop     rbp
0x180002c74  retn
```
