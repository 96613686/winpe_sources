# CCmbBxWinHost::UpdateEditBox(void)

- ea: `0x180051d9c`
- end: `0x180051eae`
- name: `?UpdateEditBox@CCmbBxWinHost@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(CCmbBxWinHost *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18004f840`
- `0x18004fca0`
- `0x180050a30`

## callees

- `0x18002720c`
- `0x1800274a0`
- `0x18004ea64`
- `0x18004ee6c`
- `0x180051d9c`
- `0x18006bb30`
- `0x180095010`

## pseudocode

```c
void __fastcall CCmbBxWinHost::UpdateEditBox(HWND *this, __int64 a2, __int64 a3, unsigned __int64 a4)
{
  HWND v5; // rax
  void *v6; // rbp
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rcx
  unsigned int v9; // eax
  void *v10; // rax
  HDC v11; // rdx

  if ( *((_DWORD *)this + 60) == 3 && ((_BYTE)this[15] & 4) != 0 )
  {
    CCmbBxWinHost::CbMessageItemHandler((CCmbBxWinHost *)this, 0, 2, a4, 0);
    return;
  }
  v5 = this[31];
  v6 = 0;
  if ( *((_DWORD *)v5 + 50) != -1 )
  {
    v7 = *((int *)v5 + 50);
    v8 = (int)(RichListBoxWndProc(this[16], 0x18Au, v7, 0) + 1);
    v9 = 2 * v8;
    if ( !is_mul_ok(v8, 2u) )
      v9 = -1;
    v10 = CW32System::PvAlloc(v9, 0x40u);
    v6 = v10;
    if ( !v10 )
    {
      (*((void (__fastcall **)(HWND *, __int64, _QWORD))*this + 38))(this, 0xFFFFFFFFLL, 0);
      return;
    }
    RichListBoxWndProc(this[16], 0x189u, v7, (__int64)v10);
  }
  *((_DWORD *)this + 30) |= 0x1000u;
  (*(void (__fastcall **)(HWND, __int64))(*(_QWORD *)this[4] + 24LL))(this[4], 12);
  CCmbBxWinHost::DrawEditFocus((CCmbBxWinHost *)this, v11);
  if ( v6 )
    CW32System::FreePv(v6);
}

```

## disassembly

```asm
0x180051d9c  push    rbx
0x180051d9e  push    rbp
0x180051d9f  push    rsi
0x180051da0  push    rdi
0x180051da1  push    r14
0x180051da3  push    r15
0x180051da5  sub     rsp, 38h
0x180051da9  cmp     dword ptr [rcx+0F0h], 3
0x180051db0  mov     rbx, rcx
0x180051db3  jnz     short loc_180051DD2
0x180051db5  test    byte ptr [rcx+78h], 4
0x180051db9  jz      short loc_180051DD2
0x180051dbb  xor     edi, edi
0x180051dbd  xor     edx, edx; HDC
0x180051dbf  mov     [rsp+68h+var_48], rdi; __int64
0x180051dc4  lea     r8d, [rdi+2]; int
0x180051dc8  call    ?CbMessageItemHandler@CCmbBxWinHost@@QEAA_JPEAUHDC__@@H_K_J@Z; CCmbBxWinHost::CbMessageItemHandler(HDC__ *,int,unsigned __int64,__int64)
0x180051dcd  jmp     loc_180051EA0
0x180051dd2  mov     rax, [rcx+0F8h]
0x180051dd9  xor     edi, edi
0x180051ddb  or      r15, 0FFFFFFFFFFFFFFFFh
0x180051ddf  mov     ebp, edi
0x180051de1  movsxd  rcx, dword ptr [rax+0C8h]
0x180051de8  cmp     ecx, r15d
0x180051deb  jz      short loc_180051E59
0x180051ded  mov     r14, rcx
0x180051df0  mov     r8, rcx; unsigned __int64
0x180051df3  mov     rcx, [rbx+80h]; HWND
0x180051dfa  xor     r9d, r9d; __int64
0x180051dfd  mov     edx, 18Ah; unsigned int
0x180051e02  call    ?RichListBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichListBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180051e07  inc     eax
0x180051e09  movsxd  rcx, eax
0x180051e0c  lea     eax, [rdi+2]
0x180051e0f  mul     rcx
0x180051e12  lea     edx, [rdi+40h]; unsigned int
0x180051e15  cmovb   rax, r15
0x180051e19  mov     ecx, eax; unsigned int
0x180051e1b  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180051e20  mov     rbp, rax
0x180051e23  test    rax, rax
0x180051e26  jnz     short loc_180051E42
0x180051e28  mov     rax, [rbx]
0x180051e2b  xor     r8d, r8d
0x180051e2e  or      edx, 0FFFFFFFFh
0x180051e31  mov     rcx, rbx
0x180051e34  mov     rax, [rax+130h]
0x180051e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e40  jmp     short loc_180051EA0
0x180051e42  mov     rcx, [rbx+80h]; HWND
0x180051e49  mov     r9, rax; __int64
0x180051e4c  mov     r8, r14; unsigned __int64
0x180051e4f  mov     edx, 189h; unsigned int
0x180051e54  call    ?RichListBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichListBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180051e59  bts     dword ptr [rbx+78h], 0Ch
0x180051e5e  lea     r9, [rsp+68h+arg_0]
0x180051e63  mov     rcx, [rbx+20h]
0x180051e67  test    rbp, rbp
0x180051e6a  mov     [rsp+68h+arg_0], di
0x180051e6f  cmovnz  r9, rbp
0x180051e73  mov     [rsp+68h+var_48], rdi
0x180051e78  xor     r8d, r8d
0x180051e7b  mov     rax, [rcx]
0x180051e7e  lea     edx, [r8+0Ch]
0x180051e82  mov     rax, [rax+18h]
0x180051e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e8b  mov     rcx, rbx; this
0x180051e8e  call    ?DrawEditFocus@CCmbBxWinHost@@QEAAXPEAUHDC__@@@Z; CCmbBxWinHost::DrawEditFocus(HDC__ *)
0x180051e93  test    rbp, rbp
0x180051e96  jz      short loc_180051EA0
0x180051e98  mov     rcx, rbp; lpMem
0x180051e9b  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180051ea0  add     rsp, 38h
0x180051ea4  pop     r15
0x180051ea6  pop     r14
0x180051ea8  pop     rdi
0x180051ea9  pop     rsi
0x180051eaa  pop     rbp
0x180051eab  pop     rbx
0x180051eac  retn
```
