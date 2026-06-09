# NetworkIncident::FindLCA(int,int *)

- ea: `0x18000ade4`
- end: `0x18000aeeb`
- name: `?FindLCA@NetworkIncident@@AEAAPEAVProblemNode@@HPEAH@Z`
- size: `263`
- prototype: `struct ProblemNode *__fastcall(NetworkIncident *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b098`

## callees

- `0x1800035a8`
- `0x18000ade4`
- `0x18000d634`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## string_xrefs

- `0x18000ae94`: `Error: Failed while trying to find least common parent to root causes. HRESULT 0x%x.`
- `0x18000ae8b`: `Error: Could not find least common parent to root causes. HRESULT 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct ProblemNode *__fastcall NetworkIncident::FindLCA(NetworkIncident *this, int a2, int *a3)
{
  int v3; // ebp
  int i; // ebx
  struct ProblemNode *result; // rax
  const unsigned __int16 *v9; // r8
  __int64 v10; // [rsp+30h] [rbp-D8h] BYREF
  struct ProblemNode *v11; // [rsp+38h] [rbp-D0h]
  int v12; // [rsp+40h] [rbp-C8h]
  int v13; // [rsp+44h] [rbp-C4h]
  unsigned __int16 v14[64]; // [rsp+50h] [rbp-B8h] BYREF

  v3 = 0;
  for ( i = 0; i < a2; ++i )
  {
    v10 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * a3[i]);
    v11 = 0;
    v13 = 0;
    v12 = a2;
    v3 = IterateOverNodes(1, v10, &v10, FindLCACallback, 0);
    if ( v3 < 0 )
      break;
    result = v11;
    if ( v11 )
      return result;
  }
  if ( *((_QWORD *)this + 27) )
  {
    memset_0(v14, 0, sizeof(v14));
    v9 = L"Error: Failed while trying to find least common parent to root causes. HRESULT 0x%x.";
    if ( v3 >= 0 )
      v9 = L"Error: Could not find least common parent to root causes. HRESULT 0x%x.";
    StringCchPrintfW(v14, 0x40u, v9, (unsigned int)v3);
    (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 27) + 96LL))(
      *((_QWORD *)this + 27),
      0,
      v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ade4  push    rbx
0x18000ade6  push    rbp
0x18000ade7  push    rsi
0x18000ade8  push    rdi
0x18000ade9  push    r14
0x18000adeb  sub     rsp, 0E0h
0x18000adf2  mov     rax, cs:__security_cookie
0x18000adf9  xor     rax, rsp
0x18000adfc  mov     [rsp+108h+var_38], rax
0x18000ae04  xor     ebp, ebp
0x18000ae06  mov     r14, r8
0x18000ae09  xor     ebx, ebx
0x18000ae0b  mov     esi, edx
0x18000ae0d  mov     rdi, rcx
0x18000ae10  cmp     ebx, esi
0x18000ae12  jge     short loc_18000AE6F
0x18000ae14  movsxd  rax, ebx
0x18000ae17  lea     r9, ?FindLCACallback@@YAJPEAVProblemNode@@PEAX@Z; FindLCACallback(ProblemNode *,void *)
0x18000ae1e  lea     r8, [rsp+108h+var_D8]
0x18000ae23  mov     [rsp+108h+var_E8], 0
0x18000ae2b  movsxd  rcx, dword ptr [r14+rax*4]
0x18000ae2f  mov     rax, [rdi+20h]
0x18000ae33  mov     rdx, [rax+rcx*8]
0x18000ae37  mov     ecx, 1
0x18000ae3c  mov     [rsp+108h+var_D8], rdx
0x18000ae41  mov     [rsp+108h+var_D0], 0
0x18000ae4a  mov     [rsp+108h+var_C4], 0
0x18000ae52  mov     [rsp+108h+var_C8], esi
0x18000ae56  call    ?IterateOverNodes@@YAJW4NodeIterateDirection@@PEAVProblemNode@@PEAXP6AJ12@ZH@Z; IterateOverNodes(NodeIterateDirection,ProblemNode *,void *,long (*)(ProblemNode *,void *),int)
0x18000ae5b  mov     ebp, eax
0x18000ae5d  test    eax, eax
0x18000ae5f  js      short loc_18000AE6F
0x18000ae61  mov     rax, [rsp+108h+var_D0]
0x18000ae66  test    rax, rax
0x18000ae69  jnz     short loc_18000AECD
0x18000ae6b  inc     ebx
0x18000ae6d  jmp     short loc_18000AE10
0x18000ae6f  cmp     qword ptr [rdi+0D8h], 0
0x18000ae77  jz      short loc_18000AECB
0x18000ae79  xor     edx, edx; Val
0x18000ae7b  lea     rcx, [rsp+108h+var_B8]; void *
0x18000ae80  mov     r8d, 80h; Size
0x18000ae86  call    memset_0
0x18000ae8b  lea     rax, aErrorCouldNotF; "Error: Could not find least common pare"...
0x18000ae92  test    ebp, ebp
0x18000ae94  lea     r8, aErrorFailedWhi; "Error: Failed while trying to find leas"...
0x18000ae9b  mov     r9d, ebp
0x18000ae9e  cmovns  r8, rax; unsigned __int16 *
0x18000aea2  lea     rcx, [rsp+108h+var_B8]; unsigned __int16 *
0x18000aea7  mov     edx, 40h ; '@'; unsigned __int64
0x18000aeac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000aeb1  mov     rcx, [rdi+0D8h]
0x18000aeb8  lea     r8, [rsp+108h+var_B8]
0x18000aebd  xor     edx, edx
0x18000aebf  mov     rax, [rcx]
0x18000aec2  mov     rax, [rax+60h]
0x18000aec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecb  xor     eax, eax
0x18000aecd  mov     rcx, [rsp+108h+var_38]
0x18000aed5  xor     rcx, rsp; StackCookie
0x18000aed8  call    __security_check_cookie
0x18000aedd  add     rsp, 0E0h
0x18000aee4  pop     r14
0x18000aee6  pop     rdi
0x18000aee7  pop     rsi
0x18000aee8  pop     rbp
0x18000aee9  pop     rbx
0x18000aeea  retn
```
