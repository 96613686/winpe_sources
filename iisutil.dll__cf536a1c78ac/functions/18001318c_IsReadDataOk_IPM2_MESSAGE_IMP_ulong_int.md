# IsReadDataOk(IPM2_MESSAGE_IMP *,ulong,int)

- ea: `0x18001318c`
- end: `0x18001340a`
- name: `?IsReadDataOk@@YAHPEAVIPM2_MESSAGE_IMP@@KH@Z`
- size: `638`
- prototype: `__int64 __fastcall(struct IPM2_MESSAGE_IMP *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a430`

## callees

- `0x180008000`
- `0x18001318c`
- `0x18002f010`

## string_xrefs

- `0x180013284`: `IsReadDataOk`
- `0x180013351`: `IsReadDataOk`
- `0x18001328b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180013358`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`

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
    if ( (*(unsigned int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 24LL))(a1) != qword_180032F40[v5]
      && qword_180032F40[2 * (*(int (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)a1 + 16LL))(a1)] != 0x7FFFFFFF )
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
      if ( LODWORD(qword_180032F40[2 * v6 + 1]) == 2 )
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
    else if ( LODWORD(qword_180032F40[2 * v6 + 1]) == 1 )
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
0x18001318c  push    rbx
0x18001318e  push    rbp
0x18001318f  push    rsi
0x180013190  push    rdi
0x180013191  sub     rsp, 48h
0x180013195  cmp     dword ptr [rcx+0Ch], 0
0x180013199  mov     esi, r8d
0x18001319c  mov     rdi, rcx
0x18001319f  jnz     loc_180013400
0x1800131a5  cmp     edx, 10h
0x1800131a8  jb      loc_1800133DD
0x1800131ae  mov     rax, [rcx]
0x1800131b1  mov     rax, [rax+10h]
0x1800131b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ba  test    eax, eax
0x1800131bc  jle     loc_1800133AB
0x1800131c2  mov     rax, [rdi]
0x1800131c5  mov     rcx, rdi
0x1800131c8  mov     rax, [rax+10h]
0x1800131cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131d1  cmp     eax, 9
0x1800131d4  jge     loc_1800133AB
0x1800131da  mov     rax, [rdi]
0x1800131dd  mov     rcx, rdi
0x1800131e0  mov     rax, [rax+18h]
0x1800131e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131e9  cmp     eax, 7FFFFFFFh
0x1800131ee  ja      loc_1800132A8
0x1800131f4  mov     rax, [rdi]
0x1800131f7  mov     rcx, rdi
0x1800131fa  mov     rax, [rax+10h]
0x1800131fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013203  movsxd  rbx, eax
0x180013206  lea     rbp, qword_180032F40
0x18001320d  mov     rax, [rdi]
0x180013210  mov     rcx, rdi
0x180013213  add     rbx, rbx
0x180013216  mov     rax, [rax+18h]
0x18001321a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001321f  mov     eax, eax
0x180013221  cmp     rax, [rbp+rbx*8+0]
0x180013226  jnz     loc_1800132E8
0x18001322c  mov     rax, [rdi]
0x18001322f  mov     rcx, rdi
0x180013232  mov     rax, [rax+10h]
0x180013236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001323b  movsxd  rcx, eax
0x18001323e  add     rcx, rcx
0x180013241  test    esi, esi
0x180013243  jnz     loc_18001336E
0x180013249  cmp     dword ptr [rbp+rcx*8+8], 1
0x18001324e  jnz     loc_180013400
0x180013254  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18001325b  jz      short loc_18001329C
0x18001325d  mov     rax, [rdi]
0x180013260  mov     rcx, rdi
0x180013263  mov     rax, [rax+10h]
0x180013267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001326c  mov     dword ptr [rsp+68h+var_40], eax; char
0x180013270  mov     r8d, 772h; unsigned int
0x180013276  lea     rax, aDataFlowValida; "data flow validation failed on: %d \n"
0x18001327d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180013284  lea     r9, aIsreaddataok; "IsReadDataOk"
0x18001328b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180013292  mov     [rsp+68h+var_48], rax; char *
0x180013297  call    PuDbgPrint
0x18001329c  xor     eax, eax
0x18001329e  add     rsp, 48h
0x1800132a2  pop     rdi
0x1800132a3  pop     rsi
0x1800132a4  pop     rbp
0x1800132a5  pop     rbx
0x1800132a6  retn
0x1800132a8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800132af  jz      short loc_18001329C
0x1800132b1  mov     rax, [rdi]
0x1800132b4  mov     rcx, rdi
0x1800132b7  mov     rax, [rax+18h]
0x1800132bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132c0  mov     ebx, eax
0x1800132c2  mov     rcx, rdi
0x1800132c5  mov     rax, [rdi]
0x1800132c8  mov     rax, [rax+10h]
0x1800132cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d1  mov     [rsp+68h+var_38], ebx
0x1800132d5  mov     r8d, 750h
0x1800132db  mov     dword ptr [rsp+68h+var_40], eax
0x1800132df  lea     rax, aMaxSizeValidat; "max size validation failed on: %d %d\n"
0x1800132e6  jmp     short loc_18001334A
0x1800132e8  mov     rax, [rdi]
0x1800132eb  mov     rcx, rdi
0x1800132ee  mov     rax, [rax+10h]
0x1800132f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132f7  movsxd  rcx, eax
0x1800132fa  add     rcx, rcx
0x1800132fd  cmp     qword ptr [rbp+rcx*8+0], 7FFFFFFFh
0x180013306  jz      loc_18001322C
0x18001330c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180013313  jz      short loc_18001329C
0x180013315  mov     rax, [rdi]
0x180013318  mov     rcx, rdi
0x18001331b  mov     rax, [rax+18h]
0x18001331f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013324  mov     ebx, eax
0x180013326  mov     rcx, rdi
0x180013329  mov     rax, [rdi]
0x18001332c  mov     rax, [rax+10h]
0x180013330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013335  mov     [rsp+68h+var_38], ebx
0x180013339  mov     r8d, 75Bh; unsigned int
0x18001333f  mov     dword ptr [rsp+68h+var_40], eax; char
0x180013343  lea     rax, aDataTypeDataSi; "data type + data size validation failed"...
0x18001334a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180013351  lea     r9, aIsreaddataok; "IsReadDataOk"
0x180013358  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001335f  mov     [rsp+68h+var_48], rax; char *
0x180013364  call    PuDbgPrint
0x180013369  jmp     loc_18001329C
0x18001336e  cmp     dword ptr [rbp+rcx*8+8], 2
0x180013373  jnz     loc_180013400
0x180013379  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180013380  jz      loc_18001329C
0x180013386  mov     rax, [rdi]
0x180013389  mov     rcx, rdi
0x18001338c  mov     rax, [rax+10h]
0x180013390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013395  mov     dword ptr [rsp+68h+var_40], eax
0x180013399  mov     r8d, 767h
0x18001339f  lea     rax, aDataFlowValida; "data flow validation failed on: %d \n"
0x1800133a6  jmp     loc_18001327D
0x1800133ab  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800133b2  jz      loc_18001329C
0x1800133b8  mov     rax, [rdi]
0x1800133bb  mov     rcx, rdi
0x1800133be  mov     rax, [rax+10h]
0x1800133c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c7  mov     dword ptr [rsp+68h+var_40], eax
0x1800133cb  mov     r8d, 746h
0x1800133d1  lea     rax, aDataValidation; "data validation failed on: %d\n"
0x1800133d8  jmp     loc_18001327D
0x1800133dd  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800133e4  jz      loc_18001329C
0x1800133ea  mov     dword ptr [rsp+68h+var_40], edx
0x1800133ee  lea     rax, aSizeValidation; "size validation failed on: %d\n"
0x1800133f5  mov     r8d, 73Bh
0x1800133fb  jmp     loc_18001327D
0x180013400  mov     eax, 1
0x180013405  jmp     loc_18001329E
```
