# GraphicCue

- ea: `0x180004e58`
- end: `0x180004f95`
- name: `GraphicCue`
- size: `317`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180001e7c`
- `0x180003a04`
- `0x180003b5c`
- `0x18000415c`
- `0x18000443c`
- `0x180004e58`
- `0x180007010`

## pseudocode

```c
int __fastcall GraphicCue(struct _MCIGRAPHIC *a1, int a2, __int64 a3)
{
  char v4; // di
  int result; // eax
  int v7; // r14d
  signed int v8; // esi
  int v9; // esi
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rcx
  signed int v13; // eax
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  if ( (a2 & 0x10000) != 0 )
    return 274;
  v7 = a2 & 0x40000;
  if ( (a2 & 0x40000) == 0
    || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 64LL))(*((_QWORD *)a1 + 19)),
        result = DisplayCachedFrame(a1),
        result >= 0) )
  {
    v8 = 0;
    if ( (v4 & 8) != 0 && ((v8 = *(_DWORD *)(a3 + 8), v8 < 0) || v8 > (int)Duration(a1)) )
    {
      return 282;
    }
    else if ( (v4 & 0x20) != 0 )
    {
      return 0;
    }
    else
    {
      if ( (v4 & 8) != 0 )
      {
        v14 = v8;
        PutSelection(a1, &v14, 0);
      }
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 64LL))(*((_QWORD *)a1 + 19));
      if ( (v4 & 2) != 0 )
      {
        v10 = *((_QWORD *)a1 + 19);
        v14 = 0;
        (*(void (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v10 + 80LL))(v10, 0xFFFFFFFFLL, &v14);
      }
      *((_DWORD *)a1 + 72) = 529;
      result = CheckResult(v9);
      v11 = result;
      if ( *((_DWORD *)a1 + 148) && !v7 )
      {
        v12 = *((_QWORD *)a1 + 19);
        v14 = 0;
        (*(void (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v12 + 80LL))(v12, 1000, &v14);
        v13 = UndisplayCachedFrame(a1);
        if ( v13 < 0 )
          return v13;
        return v11;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004e58  push    rbx
0x180004e5a  push    rbp
0x180004e5b  push    rsi
0x180004e5c  push    rdi
0x180004e5d  push    r14
0x180004e5f  push    r15
0x180004e61  sub     rsp, 28h
0x180004e65  mov     r15, r8
0x180004e68  mov     edi, edx
0x180004e6a  mov     rbx, rcx
0x180004e6d  bt      edx, 10h
0x180004e71  jnb     short loc_180004E7D
0x180004e73  mov     eax, 112h
0x180004e78  jmp     loc_180004F88
0x180004e7d  mov     r14d, edi
0x180004e80  and     r14d, 40000h
0x180004e87  jz      short loc_180004EAC
0x180004e89  mov     rcx, [rcx+98h]
0x180004e90  mov     rax, [rcx]
0x180004e93  mov     rax, [rax+40h]
0x180004e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e9c  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004e9f  call    ?DisplayCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; DisplayCachedFrame(_MCIGRAPHIC *)
0x180004ea4  test    eax, eax
0x180004ea6  js      loc_180004F88
0x180004eac  xor     esi, esi
0x180004eae  mov     ebp, edi
0x180004eb0  and     ebp, 8
0x180004eb3  jz      short loc_180004ED3
0x180004eb5  mov     esi, [r15+8]
0x180004eb9  test    esi, esi
0x180004ebb  js      short loc_180004EC9
0x180004ebd  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004ec0  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x180004ec5  cmp     esi, eax
0x180004ec7  jle     short loc_180004ED3
0x180004ec9  mov     eax, 11Ah
0x180004ece  jmp     loc_180004F88
0x180004ed3  test    dil, 20h
0x180004ed7  jz      short loc_180004EE0
0x180004ed9  xor     eax, eax
0x180004edb  jmp     loc_180004F88
0x180004ee0  test    ebp, ebp
0x180004ee2  jz      short loc_180004EF8
0x180004ee4  xor     r8d, r8d; unsigned int *
0x180004ee7  mov     [rsp+58h+arg_8], esi
0x180004eeb  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x180004ef0  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004ef3  call    ?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z; PutSelection(_MCIGRAPHIC *,ulong *,ulong *)
0x180004ef8  mov     rcx, [rbx+98h]
0x180004eff  mov     rax, [rcx]
0x180004f02  mov     rax, [rax+40h]
0x180004f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0b  mov     esi, eax
0x180004f0d  test    dil, 2
0x180004f11  jz      short loc_180004F36
0x180004f13  mov     rcx, [rbx+98h]
0x180004f1a  lea     r8, [rsp+58h+arg_8]
0x180004f1f  mov     [rsp+58h+arg_8], 0
0x180004f27  mov     rdx, [rcx]
0x180004f2a  mov     rax, [rdx+50h]
0x180004f2e  or      edx, 0FFFFFFFFh
0x180004f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f36  mov     ecx, esi; int
0x180004f38  mov     dword ptr [rbx+120h], 211h
0x180004f42  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x180004f47  cmp     dword ptr [rbx+250h], 0
0x180004f4e  mov     edi, eax
0x180004f50  jz      short loc_180004F88
0x180004f52  test    r14d, r14d
0x180004f55  jnz     short loc_180004F88
0x180004f57  mov     rcx, [rbx+98h]
0x180004f5e  lea     r8, [rsp+58h+arg_8]
0x180004f63  mov     [rsp+58h+arg_8], r14d
0x180004f68  mov     rdx, [rcx]
0x180004f6b  mov     rax, [rdx+50h]
0x180004f6f  mov     edx, 3E8h
0x180004f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f79  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004f7c  call    ?UndisplayCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; UndisplayCachedFrame(_MCIGRAPHIC *)
0x180004f81  test    eax, eax
0x180004f83  cmovs   edi, eax
0x180004f86  mov     eax, edi
0x180004f88  add     rsp, 28h
0x180004f8c  pop     r15
0x180004f8e  pop     r14
0x180004f90  pop     rdi
0x180004f91  pop     rsi
0x180004f92  pop     rbp
0x180004f93  pop     rbx
0x180004f94  retn
```
