# AddPath(_PROCESS_ENTRY *,ushort const *)

- ea: `0x18019e7f0`
- end: `0x18019e964`
- name: `?AddPath@@YAPEAU_PATH@@PEAU_PROCESS_ENTRY@@PEBG@Z`
- size: `372`
- prototype: `struct _PATH *__fastcall(struct _PROCESS_ENTRY *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180012f54`

## callees

- `0x180008ad0`
- `0x18000f998`
- `0x180012e6c`
- `0x180013048`
- `0x1800130b4`
- `0x180027430`
- `0x18019e7f0`
- `0x1801a02c0`
- `0x1801a03ec`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019e843`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019e843`

## string_xrefs

- `0x18019e8b1`: `symsrv.dll`

## pseudocode

```c
struct _PATH *__fastcall AddPath(struct _PROCESS_ENTRY *a1, const unsigned __int16 *a2)
{
  struct _PATH *result; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  int v7; // edi
  const unsigned __int16 *v8; // rsi
  struct _PATH *v9; // rax
  _BYTE v10[560]; // [rsp+20h] [rbp-268h] BYREF
  int v11; // [rsp+250h] [rbp-38h]

  result = FindPath(a2);
  if ( !result )
  {
    v5 = pMemAlloc(0x220u);
    v6 = v5;
    if ( v5 )
    {
      v7 = 1;
      _InterlockedAdd(&dword_1802B1C0C, 1u);
      v8 = (const unsigned __int16 *)(v5 + 8);
      *(_QWORD *)v5 = 0;
      wcscpy_s_ex((unsigned __int16 *)(v5 + 8), 0x105u, a2);
      memset_0(v10, 0, 0x238u);
      DoCallback(a1, 0x70000000u, v10);
      if ( v11 != 8
        && ((dword_1802AF9CC & 0x10000000) != 0
         || !symsrvLoadLib(a1, L"symsrv.dll")
         || !qword_1802B1C48
         || (unsigned int)qword_1802B1C48(v8)) )
      {
        *(_DWORD *)(v6 + 536) = 1;
      }
      if ( !(unsigned int)symsrvPath(v8) && (!*(_DWORD *)(v6 + 536) || !(unsigned int)symsrvIsStore(a1, v8)) )
        v7 = 0;
      *(_DWORD *)(v6 + 532) = v7;
      v9 = lpMem;
      if ( lpMem )
      {
        while ( *(_QWORD *)v9 )
          v9 = *(struct _PATH **)v9;
        *(_QWORD *)v9 = v6;
      }
      else
      {
        lpMem = (struct _PATH *)v6;
      }
      _InterlockedDecrement(&dword_1802B1C0C);
      return (struct _PATH *)v6;
    }
    else
    {
      SetLastError(8u);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18019e7f0  mov     [rsp+arg_10], rbx
0x18019e7f5  mov     [rsp+arg_18], rbp
0x18019e7fa  push    rsi
0x18019e7fb  push    rdi
0x18019e7fc  push    r14
0x18019e7fe  sub     rsp, 270h
0x18019e805  mov     rax, cs:__security_cookie
0x18019e80c  xor     rax, rsp
0x18019e80f  mov     [rsp+288h+var_28], rax
0x18019e817  mov     rbp, rcx
0x18019e81a  mov     r14, rdx
0x18019e81d  mov     rcx, rdx; unsigned __int16 *
0x18019e820  call    ?FindPath@@YAPEAU_PATH@@PEBG@Z; FindPath(ushort const *)
0x18019e825  test    rax, rax
0x18019e828  jnz     loc_18019E93C
0x18019e82e  mov     ecx, 220h; dwBytes
0x18019e833  call    pMemAlloc
0x18019e838  mov     rbx, rax
0x18019e83b  test    rax, rax
0x18019e83e  jnz     short loc_18019E850
0x18019e840  lea     ecx, [rax+8]; dwErrCode
0x18019e843  call    cs:__imp_SetLastError
0x18019e849  xor     eax, eax
0x18019e84b  jmp     loc_18019E93C
0x18019e850  mov     edi, 1
0x18019e855  lock add cs:dword_1802B1C0C, edi
0x18019e85c  lea     rsi, [rax+8]
0x18019e860  mov     qword ptr [rax], 0
0x18019e867  mov     rcx, rsi; unsigned __int16 *
0x18019e86a  mov     r8, r14; unsigned __int16 *
0x18019e86d  mov     edx, 105h; unsigned __int64
0x18019e872  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18019e877  xor     edx, edx; Val
0x18019e879  lea     rcx, [rsp+288h+var_268]; void *
0x18019e87e  mov     r8d, 238h; Size
0x18019e884  call    memset_0
0x18019e889  lea     r8, [rsp+288h+var_268]; void *
0x18019e88e  mov     edx, 70000000h; unsigned int
0x18019e893  mov     rcx, rbp; struct _PROCESS_ENTRY *
0x18019e896  call    ?DoCallback@@YAHPEAU_PROCESS_ENTRY@@KPEAX@Z; DoCallback(_PROCESS_ENTRY *,ulong,void *)
0x18019e89b  cmp     [rsp+288h+var_38], 8
0x18019e8a3  jz      short loc_18019E8E2
0x18019e8a5  test    cs:dword_1802AF9CC, 10000000h
0x18019e8af  jnz     short loc_18019E8DC
0x18019e8b1  lea     rdx, aSymsrvDll_1; "symsrv.dll"
0x18019e8b8  mov     rcx, rbp; struct _PROCESS_ENTRY *
0x18019e8bb  call    ?symsrvLoadLib@@YA_NPEAU_PROCESS_ENTRY@@PEBG@Z; symsrvLoadLib(_PROCESS_ENTRY *,ushort const *)
0x18019e8c0  test    al, al
0x18019e8c2  jz      short loc_18019E8DC
0x18019e8c4  mov     rax, cs:qword_1802B1C48
0x18019e8cb  test    rax, rax
0x18019e8ce  jz      short loc_18019E8DC
0x18019e8d0  mov     rcx, rsi
0x18019e8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e8d8  test    eax, eax
0x18019e8da  jz      short loc_18019E8E2
0x18019e8dc  mov     [rbx+218h], edi
0x18019e8e2  mov     rcx, rsi; unsigned __int16 *
0x18019e8e5  call    ?symsrvPath@@YAHPEBG@Z; symsrvPath(ushort const *)
0x18019e8ea  test    eax, eax
0x18019e8ec  jnz     short loc_18019E907
0x18019e8ee  cmp     [rbx+218h], eax
0x18019e8f4  jz      short loc_18019E905
0x18019e8f6  mov     rdx, rsi; unsigned __int16 *
0x18019e8f9  mov     rcx, rbp; struct _PROCESS_ENTRY *
0x18019e8fc  call    ?symsrvIsStore@@YAHPEAU_PROCESS_ENTRY@@PEBG@Z; symsrvIsStore(_PROCESS_ENTRY *,ushort const *)
0x18019e901  test    eax, eax
0x18019e903  jnz     short loc_18019E907
0x18019e905  xor     edi, edi
0x18019e907  mov     [rbx+214h], edi
0x18019e90d  mov     rax, cs:lpMem
0x18019e914  test    rax, rax
0x18019e917  jz      short loc_18019E92B
0x18019e919  mov     rcx, [rax]
0x18019e91c  test    rcx, rcx
0x18019e91f  jz      short loc_18019E926
0x18019e921  mov     rax, rcx
0x18019e924  jmp     short loc_18019E919
0x18019e926  mov     [rax], rbx
0x18019e929  jmp     short loc_18019E932
0x18019e92b  mov     cs:lpMem, rbx
0x18019e932  lock dec cs:dword_1802B1C0C
0x18019e939  mov     rax, rbx
0x18019e93c  mov     rcx, [rsp+288h+var_28]
0x18019e944  xor     rcx, rsp; StackCookie
0x18019e947  call    __security_check_cookie
0x18019e94c  lea     r11, [rsp+288h+var_18]
0x18019e954  mov     rbx, [r11+30h]
0x18019e958  mov     rbp, [r11+38h]
0x18019e95c  mov     rsp, r11
0x18019e95f  pop     r14
0x18019e961  pop     rdi
0x18019e962  pop     rsi
0x18019e963  retn
```
