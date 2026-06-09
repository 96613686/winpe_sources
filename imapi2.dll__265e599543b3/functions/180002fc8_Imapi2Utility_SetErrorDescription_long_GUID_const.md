# Imapi2Utility::SetErrorDescription(long,_GUID const &)

- ea: `0x180002fc8`
- end: `0x1800030df`
- name: `?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z`
- size: `279`
- prototype: `void __fastcall(DWORD dwMessageId, int, const struct _GUID *)`
- caller_count: `123`
- callee_count: `2`
- tags: ``

## callers

- `0x180001890`
- `0x180001f50`
- `0x180002750`
- `0x1800028d0`
- `0x180002da0`
- `0x1800030f0`
- `0x180003b00`
- `0x1800053f0`
- `0x180008510`
- `0x180008954`
- `0x1800095c0`
- `0x180009640`
- `0x18000b080`
- `0x18000b510`
- `0x18000bf20`
- `0x18000cc20`
- `0x18000e850`
- `0x18000f970`
- `0x180017300`
- `0x18001d0e0`
- `0x18001dd30`
- `0x180021610`
- `0x1800216c0`
- `0x180021890`
- `0x1800219f0`
- `0x180021b40`
- `0x180021bc0`
- `0x180021eb0`
- `0x180022160`
- `0x1800222d0`
- `0x180022360`
- `0x1800223f0`
- `0x180022550`
- `0x180022e8c`
- `0x1800234a0`
- `0x180023520`
- `0x1800235c0`
- `0x180025508`
- `0x180025dd0`
- `0x180026ff0`
- `0x180027170`
- `0x1800278b0`
- `0x180027990`
- `0x1800279f0`
- `0x180027b10`
- `0x180027c20`
- `0x180028d20`
- `0x1800292e0`
- `0x1800294a0`
- `0x180029530`

## callees

- `0x180002fc8`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800030cc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800030cc`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180003064`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180003064`
- `KERNEL32!FormatMessageW` at `0x18000301c`
- `KERNEL32!FormatMessageW` at `0x18000301c`
- `KERNEL32!LocalFree` at `0x180003073`
- `KERNEL32!LocalFree` at `0x180003073`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Imapi2Utility::SetErrorDescription(DWORD dwMessageId, __int64 a2, const struct _GUID *a3)
{
  IErrorInfo *perrinfo; // [rsp+40h] [rbp-18h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+70h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  pperrinfo = 0;
  perrinfo = 0;
  hMem = 0;
  FormatMessageW(0x900u, hModule, dwMessageId, 0x400u, (LPWSTR)&hMem, 0, 0);
  if ( hMem )
  {
    if ( CreateErrorInfo(&pperrinfo) >= 0 )
    {
      ((void (__fastcall *)(ICreateErrorInfo *, HLOCAL))pperrinfo->lpVtbl->SetDescription)(pperrinfo, hMem);
      ((void (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a2);
      if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
             pperrinfo,
             &IID_IErrorInfo,
             &perrinfo) >= 0 )
        SetErrorInfo(0, perrinfo);
    }
    LocalFree(hMem);
  }
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
}

```

## disassembly

```asm
0x180002fc8  mov     rax, rsp
0x180002fcb  mov     [rax+10h], rdx
0x180002fcf  push    rdi
0x180002fd0  sub     rsp, 50h
0x180002fd4  mov     rdi, rdx
0x180002fd7  mov     qword ptr [rax+18h], 0
0x180002fdf  mov     qword ptr [rax-18h], 0
0x180002fe7  mov     qword ptr [rax+20h], 0
0x180002fef  mov     qword ptr [rax-28h], 0
0x180002ff7  mov     dword ptr [rax-30h], 0
0x180002ffe  lea     rax, [rax+20h]
0x180003002  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x180003007  mov     r9d, 400h; dwLanguageId
0x18000300d  mov     r8d, ecx; dwMessageId
0x180003010  mov     rdx, cs:hModule; lpSource
0x180003017  mov     ecx, 900h; dwFlags
0x18000301c  call    cs:__imp_FormatMessageW
0x180003022  nop
0x180003023  cmp     [rsp+58h+hMem], 0
0x180003029  jnz     short loc_18000305F
0x18000302b  mov     rcx, [rsp+58h+perrinfo]
0x180003030  test    rcx, rcx
0x180003033  jz      short loc_180003042
0x180003035  mov     rax, [rcx]
0x180003038  mov     rax, [rax+10h]
0x18000303c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003041  nop
0x180003042  mov     rcx, [rsp+58h+pperrinfo]
0x180003047  test    rcx, rcx
0x18000304a  jz      short loc_180003059
0x18000304c  mov     rax, [rcx]
0x18000304f  mov     rax, [rax+10h]
0x180003053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003058  nop
0x180003059  add     rsp, 50h
0x18000305d  pop     rdi
0x18000305e  retn
0x18000305f  lea     rcx, [rsp+58h+pperrinfo]; pperrinfo
0x180003064  call    cs:__imp_CreateErrorInfo
0x18000306a  test    eax, eax
0x18000306c  jns     short loc_18000307B
0x18000306e  mov     rcx, [rsp+58h+hMem]; hMem
0x180003073  call    cs:__imp_LocalFree
0x180003079  jmp     short loc_18000302B
0x18000307b  mov     rcx, [rsp+58h+pperrinfo]
0x180003080  mov     rax, [rcx]
0x180003083  mov     rdx, [rsp+58h+hMem]
0x180003088  mov     rax, [rax+28h]
0x18000308c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003091  mov     rcx, [rsp+58h+pperrinfo]
0x180003096  mov     rax, [rcx]
0x180003099  mov     rdx, rdi
0x18000309c  mov     rax, [rax+18h]
0x1800030a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a5  mov     rcx, [rsp+58h+pperrinfo]
0x1800030aa  mov     rax, [rcx]
0x1800030ad  lea     r8, [rsp+58h+perrinfo]
0x1800030b2  lea     rdx, IID_IErrorInfo
0x1800030b9  mov     rax, [rax]
0x1800030bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c1  test    eax, eax
0x1800030c3  js      short loc_18000306E
0x1800030c5  mov     rdx, [rsp+58h+perrinfo]; perrinfo
0x1800030ca  xor     ecx, ecx; dwReserved
0x1800030cc  call    cs:__imp_SetErrorInfo
0x1800030d2  jmp     short loc_18000306E
0x1800030d4  mov     rdi, [rsp+58h+arg_8]
0x1800030d9  jmp     loc_180003023
```
