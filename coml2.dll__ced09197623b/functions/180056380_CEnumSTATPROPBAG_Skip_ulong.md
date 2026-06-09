# CEnumSTATPROPBAG::Skip(ulong)

- ea: `0x180056380`
- end: `0x180056445`
- name: `?Skip@CEnumSTATPROPBAG@@UEAAJK@Z`
- size: `197`
- prototype: `__int64 __fastcall(CEnumSTATPROPBAG *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180042800`
- `0x1800557bc`
- `0x180056380`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056410`

## pseudocode

```c
__int64 __fastcall CEnumSTATPROPBAG::Skip(CEnumSTATPROPBAG *this, int a2)
{
  __int64 v4; // rcx
  int v5; // edi
  int v6; // edx
  CSTATPROPBAGArray *v7; // rcx
  void *v8; // rcx
  unsigned int v10; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv[4]; // [rsp+28h] [rbp-30h] BYREF

  v4 = *((_QWORD *)this + 2);
  v5 = 0;
  *(_OWORD *)pv = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 24LL))(v4, 0xFFFFFFFFLL);
  if ( a2 )
  {
    do
    {
      v6 = *((_DWORD *)this + 8);
      v7 = (CSTATPROPBAGArray *)*((_QWORD *)this + 3);
      v10 = 1;
      v5 = CSTATPROPBAGArray::NextAt(v7, v6, (struct tagSTATPROPBAG *)pv, &v10);
      CoTaskMemFree(pv[0]);
      v8 = 0;
      pv[0] = 0;
      if ( v5 < 0 )
        break;
      if ( v5 == 1 )
        break;
      ++*((_DWORD *)this + 8);
      v5 = 0;
      --a2;
    }
    while ( a2 );
  }
  else
  {
    v8 = pv[0];
  }
  CoTaskMemFree(v8);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180056380  mov     [rsp+arg_8], rbx
0x180056385  mov     [rsp+arg_10], rsi
0x18005638a  push    rdi
0x18005638b  sub     rsp, 50h
0x18005638f  mov     rax, cs:__security_cookie
0x180056396  xor     rax, rsp
0x180056399  mov     [rsp+58h+var_10], rax
0x18005639e  mov     rbx, rcx
0x1800563a1  mov     esi, edx
0x1800563a3  mov     rcx, [rcx+10h]
0x1800563a7  xorps   xmm0, xmm0
0x1800563aa  or      edx, 0FFFFFFFFh
0x1800563ad  xor     edi, edi
0x1800563af  movups  xmmword ptr [rsp+58h+pv], xmm0
0x1800563b4  mov     rax, [rcx]
0x1800563b7  mov     rax, [rax+18h]
0x1800563bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563c0  test    esi, esi
0x1800563c2  jz      short loc_18005640B
0x1800563c4  mov     edx, [rbx+20h]; unsigned int
0x1800563c7  lea     r9, [rsp+58h+var_38]; unsigned int *
0x1800563cc  mov     rcx, [rbx+18h]; this
0x1800563d0  lea     r8, [rsp+58h+pv]; struct tagSTATPROPBAG *
0x1800563d5  mov     [rsp+58h+var_38], 1
0x1800563dd  call    ?NextAt@CSTATPROPBAGArray@@QEAAJKPEAUtagSTATPROPBAG@@PEAK@Z; CSTATPROPBAGArray::NextAt(ulong,tagSTATPROPBAG *,ulong *)
0x1800563e2  mov     rcx, [rsp+58h+pv]; pv
0x1800563e7  mov     edi, eax
0x1800563e9  call    cs:__imp_CoTaskMemFree
0x1800563ef  xor     ecx, ecx
0x1800563f1  mov     [rsp+58h+pv], rcx
0x1800563f6  test    edi, edi
0x1800563f8  js      short loc_180056410
0x1800563fa  cmp     edi, 1
0x1800563fd  jz      short loc_180056410
0x1800563ff  inc     dword ptr [rbx+20h]
0x180056402  xor     edi, edi
0x180056404  add     esi, 0FFFFFFFFh
0x180056407  jnz     short loc_1800563C4
0x180056409  jmp     short loc_180056410
0x18005640b  mov     rcx, [rsp+58h+pv]; pv
0x180056410  call    cs:__imp_CoTaskMemFree
0x180056416  mov     rcx, [rbx+10h]
0x18005641a  mov     rax, [rcx]
0x18005641d  mov     rax, [rax+20h]
0x180056421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056426  mov     eax, edi
0x180056428  mov     rcx, [rsp+58h+var_10]
0x18005642d  xor     rcx, rsp; StackCookie
0x180056430  call    __security_check_cookie
0x180056435  mov     rbx, [rsp+58h+arg_8]
0x18005643a  mov     rsi, [rsp+58h+arg_10]
0x18005643f  add     rsp, 50h
0x180056443  pop     rdi
0x180056444  retn
```
