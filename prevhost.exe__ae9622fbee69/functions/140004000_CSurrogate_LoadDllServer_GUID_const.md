# CSurrogate::LoadDllServer(_GUID const &)

- ea: `0x140004000`
- end: `0x1400040ca`
- name: `?LoadDllServer@CSurrogate@@UEAAJAEBU_GUID@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(CSurrogate *this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400010fc`
- `0x140004000`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000407c`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000407c`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1400040b2`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1400040b2`
- `COMCTL32!__imp_DPA_Create` at `0x140004021`
- `COMCTL32!__imp_DPA_Create` at `0x140004021`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x140004094`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x140004094`

## pseudocode

```c
__int64 __fastcall CSurrogate::LoadDllServer(CSurrogate *this, const struct _GUID *a2)
{
  HDPA v4; // rax
  void *v5; // rdi
  __int64 v6; // rcx
  IID v7; // xmm0
  HRESULT v8; // ebx

  if ( (*((_QWORD *)this + 3) || (v4 = DPA_Create(8), (*((_QWORD *)this + 3) = v4) != 0))
    && (v5 = operator new(0x28u)) != 0 )
  {
    v6 = *((_QWORD *)this + 1);
    *(_QWORD *)v5 = &CSurrogateFactory::`vftable';
    *((_DWORD *)v5 + 3) = 1;
    v7 = *a2;
    *((_QWORD *)v5 + 4) = v6;
    *((IID *)v5 + 1) = v7;
    v8 = CoRegisterClassObject(a2, (LPUNKNOWN)v5, 4u, 8u, (LPDWORD)v5 + 2);
    if ( v8 < 0 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    else
      DPA_InsertPtr(*((HDPA *)this + 3), 0x7FFFFFFF, v5);
  }
  else
  {
    v8 = -2147024882;
  }
  CoFreeUnusedLibraries();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140004000  mov     [rsp+arg_0], rbx
0x140004005  mov     [rsp+arg_8], rsi
0x14000400a  push    rdi
0x14000400b  sub     rsp, 30h
0x14000400f  cmp     qword ptr [rcx+18h], 0
0x140004014  mov     rbx, rdx
0x140004017  mov     rsi, rcx
0x14000401a  jnz     short loc_140004030
0x14000401c  mov     ecx, 8; cItemGrow
0x140004021  call    cs:__imp_DPA_Create
0x140004027  mov     [rsi+18h], rax
0x14000402b  test    rax, rax
0x14000402e  jz      short loc_1400040AD
0x140004030  mov     ecx, 28h ; '('; Size
0x140004035  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000403a  mov     rdi, rax
0x14000403d  test    rax, rax
0x140004040  jz      short loc_1400040AD
0x140004042  mov     rcx, [rsi+8]
0x140004046  lea     rax, ??_7CSurrogateFactory@@6B@; const CSurrogateFactory::`vftable'
0x14000404d  mov     [rdi], rax
0x140004050  mov     r9d, 8; flags
0x140004056  mov     dword ptr [rdi+0Ch], 1
0x14000405d  mov     rdx, rdi; pUnk
0x140004060  movups  xmm0, xmmword ptr [rbx]
0x140004063  mov     [rdi+20h], rcx
0x140004067  lea     rcx, [rdi+8]
0x14000406b  mov     [rsp+38h+lpdwRegister], rcx; lpdwRegister
0x140004070  lea     r8d, [r9-4]; dwClsContext
0x140004074  mov     rcx, rbx; rclsid
0x140004077  movdqu  xmmword ptr [rdi+10h], xmm0
0x14000407c  call    cs:__imp_CoRegisterClassObject
0x140004082  mov     ebx, eax
0x140004084  test    eax, eax
0x140004086  js      short loc_14000409C
0x140004088  mov     rcx, [rsi+18h]; hdpa
0x14000408c  mov     r8, rdi; p
0x14000408f  mov     edx, 7FFFFFFFh; i
0x140004094  call    cs:__imp_DPA_InsertPtr
0x14000409a  jmp     short loc_1400040B2
0x14000409c  mov     rax, [rdi]
0x14000409f  mov     rcx, rdi
0x1400040a2  mov     rax, [rax+10h]
0x1400040a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040ab  jmp     short loc_1400040B2
0x1400040ad  mov     ebx, 8007000Eh
0x1400040b2  call    cs:__imp_CoFreeUnusedLibraries
0x1400040b8  mov     rsi, [rsp+38h+arg_8]
0x1400040bd  mov     eax, ebx
0x1400040bf  mov     rbx, [rsp+38h+arg_0]
0x1400040c4  add     rsp, 30h
0x1400040c8  pop     rdi
0x1400040c9  retn
```
