# IsReadDataOk(IPM2_MESSAGE_IMP *,ulong,int)

- ea: `0x180012820`
- end: `0x180012a9d`
- name: `?IsReadDataOk@@YAHPEAVIPM2_MESSAGE_IMP@@KH@Z`
- size: `637`
- prototype: `__int64 __fastcall(struct IPM2_MESSAGE_IMP *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028630`

## callees

- `0x180007300`
- `0x180012820`
- `0x18002d010`

## string_xrefs

- `0x180012918`: `IsReadDataOk`
- `0x1800129e4`: `IsReadDataOk`
- `0x18001291f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800129eb`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`

## pseudocode

```c
__int64 __fastcall IsReadDataOk(struct IPM2_MESSAGE_IMP *a1, unsigned int a2, int a3)
{
  __int64 v5; // rbx
  int v6; // eax
  char v8; // al
  char v9; // al
  char v10; // [rsp+28h] [rbp-40h]
  char v11; // [rsp+28h] [rbp-40h]
  char v12; // [rsp+28h] [rbp-40h]

  if ( !*((_DWORD *)a1 + 3) )
  {
    if ( a2 < 0x10 )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
          0x73Bu,
          "IsReadDataOk",
          "size validation failed on: %d\n",
          a2);
      return 0;
    }
    if ( (*(int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1) <= 0
      || (*(int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1) >= 9 )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        v12 = (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
          0x746u,
          "IsReadDataOk",
          "data validation failed on: %d\n",
          v12);
      }
      return 0;
    }
    if ( (*(unsigned int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 24LL))(a1) > 0x7FFFFFFF )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 24LL))(a1);
        v8 = (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
          0x750u,
          "IsReadDataOk",
          "max size validation failed on: %d %d\n",
          v8);
      }
      return 0;
    }
    v5 = 2LL * (*(int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
    if ( (*(unsigned int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 24LL))(a1) != qword_180030F40[v5]
      && qword_180030F40[2 * (*(int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1)] != 0x7FFFFFFF )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 24LL))(a1);
        v9 = (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
          0x75Bu,
          "IsReadDataOk",
          "data type + data size validation failed on: %d %d\n",
          v9);
      }
      return 0;
    }
    v6 = (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
    if ( a3 )
    {
      if ( LODWORD(qword_180030F40[2 * v6 + 1]) == 2 )
      {
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        {
          v11 = (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
            0x767u,
            "IsReadDataOk",
            "data flow validation failed on: %d \n",
            v11);
        }
        return 0;
      }
    }
    else if ( LODWORD(qword_180030F40[2 * v6 + 1]) == 1 )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        v10 = (*(__int64 (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1);
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
          0x772u,
          "IsReadDataOk",
          "data flow validation failed on: %d \n",
          v10);
      }
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180012820  push    rbx
0x180012822  push    rbp
0x180012823  push    rsi
0x180012824  push    rdi
0x180012825  sub     rsp, 48h
0x180012829  cmp     dword ptr [rcx+0Ch], 0
0x18001282d  mov     esi, r8d
0x180012830  mov     rdi, rcx
0x180012833  jnz     loc_180012A93
0x180012839  cmp     edx, 10h
0x18001283c  jb      loc_180012A70
0x180012842  mov     rax, [rcx]
0x180012845  mov     rax, [rax+10h]
0x180012849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001284e  test    eax, eax
0x180012850  jle     loc_180012A3E
0x180012856  mov     rax, [rdi]
0x180012859  mov     rcx, rdi
0x18001285c  mov     rax, [rax+10h]
0x180012860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012865  cmp     eax, 9
0x180012868  jge     loc_180012A3E
0x18001286e  mov     rax, [rdi]
0x180012871  mov     rcx, rdi
0x180012874  mov     rax, [rax+18h]
0x180012878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001287d  cmp     eax, 7FFFFFFFh
0x180012882  ja      loc_18001293B
0x180012888  mov     rax, [rdi]
0x18001288b  mov     rcx, rdi
0x18001288e  mov     rax, [rax+10h]
0x180012892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012897  movsxd  rbx, eax
0x18001289a  lea     rbp, qword_180030F40
0x1800128a1  mov     rax, [rdi]
0x1800128a4  mov     rcx, rdi
0x1800128a7  add     rbx, rbx
0x1800128aa  mov     rax, [rax+18h]
0x1800128ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b3  mov     eax, eax
0x1800128b5  cmp     rax, [rbp+rbx*8+0]
0x1800128ba  jnz     loc_18001297B
0x1800128c0  mov     rax, [rdi]
0x1800128c3  mov     rcx, rdi
0x1800128c6  mov     rax, [rax+10h]
0x1800128ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128cf  movsxd  rcx, eax
0x1800128d2  add     rcx, rcx
0x1800128d5  test    esi, esi
0x1800128d7  jnz     loc_180012A01
0x1800128dd  cmp     dword ptr [rbp+rcx*8+8], 1
0x1800128e2  jnz     loc_180012A93
0x1800128e8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800128ef  jz      short loc_180012930
0x1800128f1  mov     rax, [rdi]
0x1800128f4  mov     rcx, rdi
0x1800128f7  mov     rax, [rax+10h]
0x1800128fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012900  mov     dword ptr [rsp+68h+var_40], eax; char
0x180012904  mov     r8d, 772h; unsigned int
0x18001290a  lea     rax, aDataFlowValida; "data flow validation failed on: %d \n"
0x180012911  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180012918  lea     r9, aIsreaddataok; "IsReadDataOk"
0x18001291f  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012926  mov     [rsp+68h+var_48], rax; char *
0x18001292b  call    PuDbgPrint
0x180012930  xor     eax, eax
0x180012932  add     rsp, 48h
0x180012936  pop     rdi
0x180012937  pop     rsi
0x180012938  pop     rbp
0x180012939  pop     rbx
0x18001293a  retn
0x18001293b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180012942  jz      short loc_180012930
0x180012944  mov     rax, [rdi]
0x180012947  mov     rcx, rdi
0x18001294a  mov     rax, [rax+18h]
0x18001294e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012953  mov     ebx, eax
0x180012955  mov     rcx, rdi
0x180012958  mov     rax, [rdi]
0x18001295b  mov     rax, [rax+10h]
0x18001295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012964  mov     [rsp+68h+var_38], ebx
0x180012968  mov     r8d, 750h
0x18001296e  mov     dword ptr [rsp+68h+var_40], eax
0x180012972  lea     rax, aMaxSizeValidat; "max size validation failed on: %d %d\n"
0x180012979  jmp     short loc_1800129DD
0x18001297b  mov     rax, [rdi]
0x18001297e  mov     rcx, rdi
0x180012981  mov     rax, [rax+10h]
0x180012985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001298a  movsxd  rcx, eax
0x18001298d  add     rcx, rcx
0x180012990  cmp     qword ptr [rbp+rcx*8+0], 7FFFFFFFh
0x180012999  jz      loc_1800128C0
0x18001299f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800129a6  jz      short loc_180012930
0x1800129a8  mov     rax, [rdi]
0x1800129ab  mov     rcx, rdi
0x1800129ae  mov     rax, [rax+18h]
0x1800129b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b7  mov     ebx, eax
0x1800129b9  mov     rcx, rdi
0x1800129bc  mov     rax, [rdi]
0x1800129bf  mov     rax, [rax+10h]
0x1800129c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129c8  mov     [rsp+68h+var_38], ebx
0x1800129cc  mov     r8d, 75Bh; unsigned int
0x1800129d2  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800129d6  lea     rax, aDataTypeDataSi; "data type + data size validation failed"...
0x1800129dd  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800129e4  lea     r9, aIsreaddataok; "IsReadDataOk"
0x1800129eb  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800129f2  mov     [rsp+68h+var_48], rax; char *
0x1800129f7  call    PuDbgPrint
0x1800129fc  jmp     loc_180012930
0x180012a01  cmp     dword ptr [rbp+rcx*8+8], 2
0x180012a06  jnz     loc_180012A93
0x180012a0c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180012a13  jz      loc_180012930
0x180012a19  mov     rax, [rdi]
0x180012a1c  mov     rcx, rdi
0x180012a1f  mov     rax, [rax+10h]
0x180012a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a28  mov     dword ptr [rsp+68h+var_40], eax
0x180012a2c  mov     r8d, 767h
0x180012a32  lea     rax, aDataFlowValida; "data flow validation failed on: %d \n"
0x180012a39  jmp     loc_180012911
0x180012a3e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180012a45  jz      loc_180012930
0x180012a4b  mov     rax, [rdi]
0x180012a4e  mov     rcx, rdi
0x180012a51  mov     rax, [rax+10h]
0x180012a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a5a  mov     dword ptr [rsp+68h+var_40], eax
0x180012a5e  mov     r8d, 746h
0x180012a64  lea     rax, aDataValidation; "data validation failed on: %d\n"
0x180012a6b  jmp     loc_180012911
0x180012a70  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180012a77  jz      loc_180012930
0x180012a7d  mov     dword ptr [rsp+68h+var_40], edx
0x180012a81  lea     rax, aSizeValidation; "size validation failed on: %d\n"
0x180012a88  mov     r8d, 73Bh
0x180012a8e  jmp     loc_180012911
0x180012a93  mov     eax, 1
0x180012a98  jmp     loc_180012932
```
