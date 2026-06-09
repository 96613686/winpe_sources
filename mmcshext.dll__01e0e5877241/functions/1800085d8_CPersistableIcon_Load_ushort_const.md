# CPersistableIcon::Load(ushort const *)

- ea: `0x1800085d8`
- end: `0x180008796`
- name: `?Load@CPersistableIcon@@QEAAJPEBG@Z`
- size: `446`
- prototype: `__int64 __fastcall(CPersistableIcon *__hidden this, WCHAR *pwcsName)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002160`

## callees

- `0x180002c40`
- `0x1800083b8`
- `0x1800085d8`
- `0x18000b010`

## import_xrefs

- `ole32!StgOpenStorage` at `0x18000861d`
- `ole32!StgOpenStorage` at `0x18000861d`

## pseudocode

```c
__int64 __fastcall CPersistableIcon::Load(CPersistableIcon *this, WCHAR *pwcsName)
{
  HRESULT v3; // ebx
  struct IStorage *v5; // [rsp+60h] [rbp+20h] BYREF
  IStorage *ppstgOpen; // [rsp+68h] [rbp+28h] BYREF

  v5 = 0;
  ppstgOpen = 0;
  v3 = StgOpenStorage(pwcsName, 0, 0x20u, 0, 0, &ppstgOpen);
  if ( v3 >= 0 )
  {
    if ( v5 )
      ((void (__fastcall *)(struct IStorage *))v5->lpVtbl->Release)(v5);
    v5 = 0;
    v3 = ((__int64 (__fastcall *)(IStorage *, const wchar_t *, _QWORD, __int64, _QWORD, _DWORD, struct IStorage **))ppstgOpen->lpVtbl->OpenStorage)(
           ppstgOpen,
           L"Custom Data",
           0,
           16,
           0,
           0,
           &v5);
    if ( v3 >= 0 )
    {
      v3 = CPersistableIcon::Load(this, v5);
      if ( v5 )
        ((void (__fastcall *)(struct IStorage *))v5->lpVtbl->Release)(v5);
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids,
          (unsigned int)v3);
      if ( v5 )
        ((void (__fastcall *)(struct IStorage *))v5->lpVtbl->Release)(v5);
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids,
        (unsigned int)v3);
    if ( v5 )
      ((void (__fastcall *)(struct IStorage *))v5->lpVtbl->Release)(v5);
    if ( ppstgOpen )
      ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800085d8  mov     [rsp-8+arg_0], rbx
0x1800085dd  mov     [rsp-8+arg_8], rdi
0x1800085e2  push    rbp
0x1800085e3  mov     rbp, rsp
0x1800085e6  sub     rsp, 40h
0x1800085ea  mov     rax, rdx
0x1800085ed  mov     rdi, rcx
0x1800085f0  mov     [rbp+arg_10], 0
0x1800085f8  mov     [rbp+arg_18], 0
0x180008600  lea     rcx, [rbp+arg_18]
0x180008604  mov     [rsp+40h+ppstgOpen], rcx; ppstgOpen
0x180008609  mov     [rsp+40h+reserved], 0; reserved
0x180008611  xor     r9d, r9d; snbExclude
0x180008614  xor     edx, edx; pstgPriority
0x180008616  lea     r8d, [r9+20h]; grfMode
0x18000861a  mov     rcx, rax; pwcsName
0x18000861d  call    cs:__imp_StgOpenStorage
0x180008623  mov     ebx, eax
0x180008625  test    eax, eax
0x180008627  jns     short loc_18000868C
0x180008629  lea     rax, WPP_GLOBAL_Control
0x180008630  mov     rcx, cs:WPP_GLOBAL_Control
0x180008637  cmp     rcx, rax
0x18000863a  jz      short loc_18000865B
0x18000863c  cmp     byte ptr [rcx+19h], 2
0x180008640  jb      short loc_18000865B
0x180008642  mov     edx, 0Fh
0x180008647  mov     r9d, ebx
0x18000864a  lea     r8, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids
0x180008651  mov     rcx, [rcx+10h]
0x180008655  call    WPP_SF_d
0x18000865a  nop
0x18000865b  mov     rcx, [rbp+arg_10]
0x18000865f  test    rcx, rcx
0x180008662  jz      short loc_180008671
0x180008664  mov     rax, [rcx]
0x180008667  mov     rax, [rax+10h]
0x18000866b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008670  nop
0x180008671  mov     rcx, [rbp+arg_18]
0x180008675  test    rcx, rcx
0x180008678  jz      short loc_180008687
0x18000867a  mov     rax, [rcx]
0x18000867d  mov     rax, [rax+10h]
0x180008681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008686  nop
0x180008687  jmp     loc_180008784
0x18000868c  mov     rcx, [rbp+arg_10]
0x180008690  test    rcx, rcx
0x180008693  jz      short loc_1800086A2
0x180008695  mov     rax, [rcx]
0x180008698  mov     rax, [rax+10h]
0x18000869c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a1  nop
0x1800086a2  mov     [rbp+arg_10], 0
0x1800086aa  mov     rcx, [rbp+arg_18]
0x1800086ae  mov     rax, [rcx]
0x1800086b1  lea     rdx, [rbp+arg_10]
0x1800086b5  mov     [rsp+40h+var_10], rdx
0x1800086ba  mov     dword ptr [rsp+40h+ppstgOpen], 0
0x1800086c2  mov     qword ptr [rsp+40h+reserved], 0
0x1800086cb  mov     r9d, 10h
0x1800086d1  xor     r8d, r8d
0x1800086d4  lea     rdx, aCustomData; "Custom Data"
0x1800086db  mov     rax, [rax+30h]
0x1800086df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e4  mov     ebx, eax
0x1800086e6  test    eax, eax
0x1800086e8  jns     short loc_18000874A
0x1800086ea  lea     rax, WPP_GLOBAL_Control
0x1800086f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086f8  cmp     rcx, rax
0x1800086fb  jz      short loc_18000871C
0x1800086fd  cmp     byte ptr [rcx+19h], 2
0x180008701  jb      short loc_18000871C
0x180008703  mov     edx, 10h
0x180008708  mov     r9d, ebx
0x18000870b  lea     r8, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids
0x180008712  mov     rcx, [rcx+10h]
0x180008716  call    WPP_SF_d
0x18000871b  nop
0x18000871c  mov     rcx, [rbp+arg_10]
0x180008720  test    rcx, rcx
0x180008723  jz      short loc_180008732
0x180008725  mov     rax, [rcx]
0x180008728  mov     rax, [rax+10h]
0x18000872c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008731  nop
0x180008732  mov     rcx, [rbp+arg_18]
0x180008736  test    rcx, rcx
0x180008739  jz      short loc_180008748
0x18000873b  mov     rax, [rcx]
0x18000873e  mov     rax, [rax+10h]
0x180008742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008747  nop
0x180008748  jmp     short loc_180008784
0x18000874a  mov     rdx, [rbp+arg_10]; struct IStorage *
0x18000874e  mov     rcx, rdi; this
0x180008751  call    ?Load@CPersistableIcon@@QEAAJPEAUIStorage@@@Z; CPersistableIcon::Load(IStorage *)
0x180008756  mov     ebx, eax
0x180008758  mov     rcx, [rbp+arg_10]
0x18000875c  test    rcx, rcx
0x18000875f  jz      short loc_18000876E
0x180008761  mov     rax, [rcx]
0x180008764  mov     rax, [rax+10h]
0x180008768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000876d  nop
0x18000876e  mov     rcx, [rbp+arg_18]
0x180008772  test    rcx, rcx
0x180008775  jz      short loc_180008784
0x180008777  mov     rax, [rcx]
0x18000877a  mov     rax, [rax+10h]
0x18000877e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008783  nop
0x180008784  mov     eax, ebx
0x180008786  mov     rbx, [rsp+40h+arg_0]
0x18000878b  mov     rdi, [rsp+40h+arg_8]
0x180008790  add     rsp, 40h
0x180008794  pop     rbp
0x180008795  retn
```
