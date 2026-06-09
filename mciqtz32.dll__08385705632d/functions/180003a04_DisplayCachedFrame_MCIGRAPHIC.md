# DisplayCachedFrame(_MCIGRAPHIC *)

- ea: `0x180003a04`
- end: `0x180003b54`
- name: `?DisplayCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z`
- size: `336`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e58`

## callees

- `0x180001014`
- `0x180001e7c`
- `0x180003a04`
- `0x1800041fc`
- `0x180007010`

## pseudocode

```c
unsigned int __fastcall DisplayCachedFrame(struct _MCIGRAPHIC *a1)
{
  int v2; // edi
  __int64 v3; // rcx
  void *v4; // rax
  void *v5; // r8
  unsigned int *v6; // r8
  unsigned __int16 v7; // cx
  unsigned __int16 v8; // ax
  int v9; // eax
  int v10; // ecx
  int v12; // edi
  int v13; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  ReleaseCachedFrame(a1);
  v3 = *((_QWORD *)a1 + 21);
  if ( v3 )
  {
    v13 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v3 + 288LL))(v3, &v13, 0);
    if ( v13 > 0 && v2 >= 0 )
    {
      v4 = operator new[](v13);
      *((_QWORD *)a1 + 75) = v4;
      v5 = v4;
      if ( !v4 )
        goto LABEL_15;
      v2 = (*(__int64 (__fastcall **)(_QWORD, int *, void *))(**((_QWORD **)a1 + 21) + 288LL))(
             *((_QWORD *)a1 + 21),
             &v13,
             v4);
      if ( v2 < 0 )
      {
        ReleaseCachedFrame(a1);
      }
      else
      {
        v6 = (unsigned int *)*((_QWORD *)a1 + 75);
        v7 = *((_WORD *)v6 + 7);
        if ( v7 >= 0x10u || v6[8] )
          v8 = *((_WORD *)v6 + 16);
        else
          v8 = 1 << v7;
        *((_QWORD *)a1 + 76) = (char *)&v6[v8] + *v6;
      }
    }
  }
  v9 = CheckResult(v2);
  if ( v9 < 0 )
  {
    v10 = v9;
    return CheckResult(v10);
  }
LABEL_15:
  (*(void (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)a1 + 22) + 104LL))(*((_QWORD *)a1 + 22), 0, v5);
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 22) + 152LL))(*((_QWORD *)a1 + 22), 0);
  if ( v12 < 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 22) + 104LL))(*((_QWORD *)a1 + 22), 0xFFFFFFFFLL);
    ReleaseCachedFrame(a1);
    v10 = v12;
    return CheckResult(v10);
  }
  *((_DWORD *)a1 + 148) = 1;
  return 0;
}

```

## disassembly

```asm
0x180003a04  mov     [rsp+arg_8], rbx
0x180003a09  push    rdi
0x180003a0a  sub     rsp, 20h
0x180003a0e  mov     rbx, rcx
0x180003a11  xor     edi, edi
0x180003a13  call    ?ReleaseCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; ReleaseCachedFrame(_MCIGRAPHIC *)
0x180003a18  mov     rcx, [rbx+0A8h]
0x180003a1f  test    rcx, rcx
0x180003a22  jz      loc_180003AD4
0x180003a28  mov     [rsp+28h+arg_0], edi
0x180003a2c  lea     rdx, [rsp+28h+arg_0]
0x180003a31  mov     rax, [rcx]
0x180003a34  xor     r8d, r8d
0x180003a37  mov     rax, [rax+120h]
0x180003a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a43  mov     edi, eax
0x180003a45  movsxd  rax, [rsp+28h+arg_0]
0x180003a4a  test    eax, eax
0x180003a4c  jle     loc_180003AD4
0x180003a52  test    edi, edi
0x180003a54  js      short loc_180003AD4
0x180003a56  mov     rcx, rax; unsigned __int64
0x180003a59  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003a5e  mov     [rbx+258h], rax
0x180003a65  mov     r8, rax
0x180003a68  test    rax, rax
0x180003a6b  jz      short loc_180003AE8
0x180003a6d  mov     rcx, [rbx+0A8h]
0x180003a74  mov     rdx, [rcx]
0x180003a77  mov     rax, [rdx+120h]
0x180003a7e  lea     rdx, [rsp+28h+arg_0]
0x180003a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a88  mov     edi, eax
0x180003a8a  test    eax, eax
0x180003a8c  js      short loc_180003ACC
0x180003a8e  mov     r8, [rbx+258h]
0x180003a95  movzx   ecx, word ptr [r8+0Eh]
0x180003a9a  cmp     cx, 10h
0x180003a9e  jnb     short loc_180003AB1
0x180003aa0  cmp     dword ptr [r8+20h], 0
0x180003aa5  jnz     short loc_180003AB1
0x180003aa7  mov     eax, 1
0x180003aac  shl     ax, cl
0x180003aaf  jmp     short loc_180003AB6
0x180003ab1  movzx   eax, word ptr [r8+20h]
0x180003ab6  mov     ecx, [r8]
0x180003ab9  add     rcx, r8
0x180003abc  movzx   edx, ax
0x180003abf  lea     rax, [rcx+rdx*4]
0x180003ac3  mov     [rbx+260h], rax
0x180003aca  jmp     short loc_180003AD4
0x180003acc  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180003acf  call    ?ReleaseCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; ReleaseCachedFrame(_MCIGRAPHIC *)
0x180003ad4  mov     ecx, edi; int
0x180003ad6  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x180003adb  test    eax, eax
0x180003add  jns     short loc_180003AE8
0x180003adf  mov     ecx, eax; int
0x180003ae1  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x180003ae6  jmp     short loc_180003B49
0x180003ae8  mov     rcx, [rbx+0B0h]
0x180003aef  xor     edx, edx
0x180003af1  mov     rax, [rcx]
0x180003af4  mov     rax, [rax+68h]
0x180003af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afd  mov     rcx, [rbx+0B0h]
0x180003b04  xor     edx, edx
0x180003b06  mov     rax, [rcx]
0x180003b09  mov     rax, [rax+98h]
0x180003b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b15  mov     edi, eax
0x180003b17  test    eax, eax
0x180003b19  jns     short loc_180003B3D
0x180003b1b  mov     rcx, [rbx+0B0h]
0x180003b22  mov     rdx, [rcx]
0x180003b25  mov     rax, [rdx+68h]
0x180003b29  or      edx, 0FFFFFFFFh
0x180003b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b31  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180003b34  call    ?ReleaseCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; ReleaseCachedFrame(_MCIGRAPHIC *)
0x180003b39  mov     ecx, edi
0x180003b3b  jmp     short loc_180003AE1
0x180003b3d  mov     dword ptr [rbx+250h], 1
0x180003b47  xor     eax, eax
0x180003b49  mov     rbx, [rsp+28h+arg_8]
0x180003b4e  add     rsp, 20h
0x180003b52  pop     rdi
0x180003b53  retn
```
