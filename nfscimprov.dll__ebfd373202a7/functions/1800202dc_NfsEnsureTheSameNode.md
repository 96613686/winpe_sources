# NfsEnsureTheSameNode

- ea: `0x1800202dc`
- end: `0x1800203d0`
- name: `NfsEnsureTheSameNode`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f2d8`

## callees

- `0x1800202dc`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180020358`
- `msvcrt!_wcsicmp` at `0x180020358`
- `KERNEL32!Sleep` at `0x180020367`
- `KERNEL32!Sleep` at `0x180020367`
- `CLUSAPI!GetClusterGroupState` at `0x18002031e`
- `CLUSAPI!GetClusterGroupState` at `0x180020341`
- `CLUSAPI!GetClusterGroupState` at `0x18002031e`
- `CLUSAPI!GetClusterGroupState` at `0x180020341`

## string_xrefs

- `0x180020378`: `cannot move HandleClusGroup2 to the same node as where HandleClusGroup1 is`

## pseudocode

```c
__int64 __fastcall NfsEnsureTheSameNode(
        void (__fastcall ***a1)(_QWORD, __int64, const wchar_t *, __int64),
        struct _HGROUP *a2,
        struct _HGROUP *a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // edi
  DWORD cchNodeName; // [rsp+30h] [rbp-138h] BYREF
  DWORD v9[3]; // [rsp+34h] [rbp-134h] BYREF
  WCHAR String2[64]; // [rsp+40h] [rbp-128h] BYREF
  WCHAR szNodeName[64]; // [rsp+C0h] [rbp-A8h] BYREF

  cchNodeName = 64;
  if ( GetClusterGroupState(a2, szNodeName, &cchNodeName) )
  {
    v5 = 5023;
    (**a1)(a1, 3221229672LL, L"HandleClusGroup1 is not in online state", 5023);
  }
  else
  {
    v5 = 0;
    v6 = 0;
    while ( 1 )
    {
      v9[0] = 64;
      if ( GetClusterGroupState(a3, String2, v9) == ClusterGroupOnline && !_wcsicmp(szNodeName, String2) )
        break;
      Sleep(0x1388u);
      v6 += 5;
      if ( v6 >= 0x78 )
      {
        v5 = 5908;
        (**a1)(a1, 3221229672LL, L"cannot move HandleClusGroup2 to the same node as where HandleClusGroup1 is", 5908);
        return v5;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800202dc  mov     [rsp+arg_18], rbx
0x1800202e1  push    rbp
0x1800202e2  push    rsi
0x1800202e3  push    rdi
0x1800202e4  sub     rsp, 150h
0x1800202eb  mov     rax, cs:__security_cookie
0x1800202f2  xor     rax, rsp
0x1800202f5  mov     [rsp+168h+var_28], rax
0x1800202fd  mov     rax, rdx
0x180020300  mov     [rsp+168h+cchNodeName], 40h ; '@'
0x180020308  mov     rbp, r8
0x18002030b  lea     rdx, [rsp+168h+szNodeName]; lpszNodeName
0x180020313  mov     rsi, rcx
0x180020316  lea     r8, [rsp+168h+cchNodeName]; lpcchNodeName
0x18002031b  mov     rcx, rax; hGroup
0x18002031e  call    cs:__imp_GetClusterGroupState
0x180020324  test    eax, eax
0x180020326  jnz     short loc_180020389
0x180020328  xor     ebx, ebx
0x18002032a  xor     edi, edi
0x18002032c  lea     r8, [rsp+168h+var_134]; lpcchNodeName
0x180020331  mov     [rsp+168h+var_134], 40h ; '@'
0x180020339  lea     rdx, [rsp+168h+String2]; lpszNodeName
0x18002033e  mov     rcx, rbp; hGroup
0x180020341  call    cs:__imp_GetClusterGroupState
0x180020347  test    eax, eax
0x180020349  jnz     short loc_180020362
0x18002034b  lea     rdx, [rsp+168h+String2]; String2
0x180020350  lea     rcx, [rsp+168h+szNodeName]; String1
0x180020358  call    cs:__imp__wcsicmp
0x18002035e  test    eax, eax
0x180020360  jz      short loc_1800203AB
0x180020362  mov     ecx, 1388h; dwMilliseconds
0x180020367  call    cs:__imp_Sleep
0x18002036d  add     edi, 5
0x180020370  cmp     edi, 78h ; 'x'
0x180020373  jb      short loc_18002032C
0x180020375  mov     rax, [rsi]
0x180020378  lea     r8, aCannotMoveHand; "cannot move HandleClusGroup2 to the sam"...
0x18002037f  mov     ebx, 1714h
0x180020384  mov     rax, [rax]
0x180020387  jmp     short loc_18002039B
0x180020389  mov     rcx, [rsi]
0x18002038c  lea     r8, aHandleclusgrou; "HandleClusGroup1 is not in online state"
0x180020393  mov     ebx, 139Fh
0x180020398  mov     rax, [rcx]
0x18002039b  mov     r9d, ebx
0x18002039e  mov     edx, 0C0001068h
0x1800203a3  mov     rcx, rsi
0x1800203a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203ab  mov     eax, ebx
0x1800203ad  mov     rcx, [rsp+168h+var_28]
0x1800203b5  xor     rcx, rsp; StackCookie
0x1800203b8  call    __security_check_cookie
0x1800203bd  mov     rbx, [rsp+168h+arg_18]
0x1800203c5  add     rsp, 150h
0x1800203cc  pop     rdi
0x1800203cd  pop     rsi
0x1800203ce  pop     rbp
0x1800203cf  retn
```
