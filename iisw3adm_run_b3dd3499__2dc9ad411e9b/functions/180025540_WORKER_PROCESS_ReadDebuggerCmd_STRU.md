# WORKER_PROCESS::ReadDebuggerCmd(STRU *)

- ea: `0x180025540`
- end: `0x1800256d8`
- name: `?ReadDebuggerCmd@WORKER_PROCESS@@AEAAJPEAVSTRU@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(WORKER_PROCESS *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180027008`

## callees

- `0x180025540`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180025691`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025691`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800255b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800255b0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800255e6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800255e6`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x180025612`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x18002565b`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x180025612`
- `iisutil!ReadStringParameterValueFromAnyService` at `0x18002565b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002559e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002559e`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18002567c`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18002567c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800255c9`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800255c9`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180025633`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180025633`

## string_xrefs

- `0x1800255a4`: `System\CurrentControlSet\Services\WAS`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::ReadDebuggerCmd(WORKER_PROCESS *this, struct STRU *a2)
{
  int v4; // ebx
  const unsigned __int16 *v5; // r8
  int v6; // eax
  const unsigned __int16 *v7; // r8
  unsigned int v9; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[32]; // [rsp+28h] [rbp-D8h] BYREF
  const unsigned __int16 *v11; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v12[264]; // [rsp+60h] [rbp-A0h] BYREF

  v9 = 0;
  memset_0(v12, 0, 0x208u);
  STRU::STRU((STRU *)v10, v12, 0x104u);
  v4 = STRU::Copy((STRU *)v10, L"System\\CurrentControlSet\\Services\\WAS");
  if ( v4 < 0 )
    goto LABEL_11;
  v4 = STRU::Append((STRU *)v10, 0x5Cu);
  if ( v4 < 0 )
    goto LABEL_11;
  v4 = STRU::Append((STRU *)v10, *(const unsigned __int16 **)(*((_QWORD *)this + 7) + 56LL));
  if ( v4 < 0 )
    goto LABEL_11;
  v5 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  v9 = *((_DWORD *)a2 + 10);
  v6 = ReadStringParameterValueFromAnyService(v11, L"Debugger", v5, &v9);
  v4 = v6;
  if ( v6 >= 0 )
    goto LABEL_8;
  if ( v6 == -2147024662 )
  {
    v4 = STRU::Resize(a2, v9 + 2);
    if ( v4 < 0 )
      goto LABEL_11;
    v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
    v9 = *((_DWORD *)a2 + 10);
    v4 = ReadStringParameterValueFromAnyService(v11, L"Debugger", v7, &v9);
    if ( v4 < 0 )
      goto LABEL_11;
LABEL_8:
    if ( **((_WORD **)a2 + 4) && !STRU::SetLen(a2, (v9 >> 1) - 1) )
      v4 = -2147024774;
    goto LABEL_11;
  }
  if ( v6 == -2147024894 )
  {
    v4 = 0;
    **((_WORD **)a2 + 4) = 0;
    *((_DWORD *)a2 + 12) = 0;
  }
LABEL_11:
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025540  mov     [rsp-8+arg_10], rbx
0x180025545  mov     [rsp-8+arg_18], rsi
0x18002554a  push    rbp
0x18002554b  push    rdi
0x18002554c  push    r14
0x18002554e  lea     rbp, [rsp-180h]
0x180025556  sub     rsp, 280h
0x18002555d  mov     rax, cs:__security_cookie
0x180025564  xor     rax, rsp
0x180025567  mov     [rbp+190h+var_20], rax
0x18002556e  mov     rdi, rdx
0x180025571  mov     rsi, rcx
0x180025574  xor     r14d, r14d
0x180025577  lea     rcx, [rsp+290h+var_230]; void *
0x18002557c  xor     edx, edx; Val
0x18002557e  mov     [rsp+290h+var_270], r14d
0x180025583  mov     r8d, 208h; Size
0x180025589  call    memset_0
0x18002558e  mov     r8d, 104h
0x180025594  lea     rdx, [rsp+290h+var_230]
0x180025599  lea     rcx, [rsp+290h+var_268]
0x18002559e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800255a4  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WA"...
0x1800255ab  lea     rcx, [rsp+290h+var_268]
0x1800255b0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800255b6  mov     ebx, eax
0x1800255b8  test    eax, eax
0x1800255ba  js      loc_18002568C
0x1800255c0  lea     edx, [r14+5Ch]
0x1800255c4  lea     rcx, [rsp+290h+var_268]
0x1800255c9  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800255cf  mov     ebx, eax
0x1800255d1  test    eax, eax
0x1800255d3  js      loc_18002568C
0x1800255d9  mov     rdx, [rsi+38h]
0x1800255dd  lea     rcx, [rsp+290h+var_268]
0x1800255e2  mov     rdx, [rdx+38h]
0x1800255e6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800255ec  mov     ebx, eax
0x1800255ee  test    eax, eax
0x1800255f0  js      loc_18002568C
0x1800255f6  mov     eax, [rdi+28h]
0x1800255f9  lea     r9, [rsp+290h+var_270]
0x1800255fe  mov     r8, [rdi+20h]
0x180025602  lea     rdx, aDebugger; "Debugger"
0x180025609  mov     rcx, [rsp+290h+var_248]
0x18002560e  mov     [rsp+290h+var_270], eax
0x180025612  call    cs:__imp_?ReadStringParameterValueFromAnyService@@YAJPEBG00PEAK@Z; ReadStringParameterValueFromAnyService(ushort const *,ushort const *,ushort const *,ulong *)
0x180025618  mov     ebx, eax
0x18002561a  test    eax, eax
0x18002561c  jns     short loc_180025667
0x18002561e  cmp     eax, 800700EAh
0x180025623  jnz     loc_1800256C0
0x180025629  mov     edx, [rsp+290h+var_270]
0x18002562d  mov     rcx, rdi
0x180025630  add     edx, 2
0x180025633  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180025639  mov     ebx, eax
0x18002563b  test    eax, eax
0x18002563d  js      short loc_18002568C
0x18002563f  mov     eax, [rdi+28h]
0x180025642  lea     r9, [rsp+290h+var_270]
0x180025647  mov     r8, [rdi+20h]
0x18002564b  lea     rdx, aDebugger; "Debugger"
0x180025652  mov     rcx, [rsp+290h+var_248]
0x180025657  mov     [rsp+290h+var_270], eax
0x18002565b  call    cs:__imp_?ReadStringParameterValueFromAnyService@@YAJPEBG00PEAK@Z; ReadStringParameterValueFromAnyService(ushort const *,ushort const *,ushort const *,ulong *)
0x180025661  mov     ebx, eax
0x180025663  test    eax, eax
0x180025665  js      short loc_18002568C
0x180025667  mov     rax, [rdi+20h]
0x18002566b  cmp     [rax], r14w
0x18002566f  jz      short loc_18002568C
0x180025671  mov     edx, [rsp+290h+var_270]
0x180025675  mov     rcx, rdi
0x180025678  shr     edx, 1
0x18002567a  dec     edx
0x18002567c  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180025682  test    al, al
0x180025684  mov     ecx, 8007007Ah
0x180025689  cmovz   ebx, ecx
0x18002568c  lea     rcx, [rsp+290h+var_268]
0x180025691  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180025697  mov     eax, ebx
0x180025699  mov     rcx, [rbp+190h+var_20]
0x1800256a0  xor     rcx, rsp; StackCookie
0x1800256a3  call    __security_check_cookie
0x1800256a8  lea     r11, [rsp+290h+var_10]
0x1800256b0  mov     rbx, [r11+30h]
0x1800256b4  mov     rsi, [r11+38h]
0x1800256b8  mov     rsp, r11
0x1800256bb  pop     r14
0x1800256bd  pop     rdi
0x1800256be  pop     rbp
0x1800256bf  retn
0x1800256c0  cmp     eax, 80070002h
0x1800256c5  jnz     short loc_18002568C
0x1800256c7  mov     rcx, [rdi+20h]
0x1800256cb  mov     ebx, r14d
0x1800256ce  mov     [rcx], r14w
0x1800256d2  mov     [rdi+30h], r14d
0x1800256d6  jmp     short loc_18002568C
```
