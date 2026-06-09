# NtWin32LiveSystemProvider::GetThreadName(void *,void *,ushort *,ulong)

- ea: `0x180024e20`
- end: `0x180024f56`
- name: `?GetThreadName@NtWin32LiveSystemProvider@@UEAAJPEAX0PEAGK@Z`
- size: `310`
- prototype: `int(NtWin32LiveSystemProvider *__hidden this, void *, void *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180024e20`
- `0x180026ef4`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::GetThreadName(
        NtWin32LiveSystemProvider *this,
        void *a2,
        void *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  MiniDumpOsImports *v8; // rcx
  _QWORD *v9; // r14
  __int64 result; // rax
  signed int v11; // ebx
  int InformationThread; // ebp
  __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  unsigned __int64 v15; // rcx
  unsigned __int16 *v16; // rcx
  unsigned int v17[22]; // [rsp+30h] [rbp-58h] BYREF

  v17[0] = 0;
  if ( !g_NtDllCallsMdwd )
    return 2147500033LL;
  v9 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 8LL))(
                   *((_QWORD *)this + 6),
                   2 * a5 + 16);
  if ( !v9 )
    return 2147942414LL;
  v11 = 0;
  InformationThread = MiniDumpOsImports::NtQueryInformationThread(
                        v8,
                        a3,
                        ThreadDescriptorTableEntry|0x20,
                        v9,
                        2 * a5 + 16,
                        v17);
  if ( InformationThread >= 0 )
  {
    v13 = a5;
    if ( a5 - 1 > 0x7FFFFFFE )
    {
      v11 = -2147024809;
      if ( a5 )
        *a4 = 0;
    }
    else
    {
      v14 = (unsigned __int16 *)v9[1];
      v15 = (unsigned __int64)*(unsigned __int16 *)v9 >> 1;
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *a4++ = *v14++;
        --v15;
        --v13;
      }
      while ( v13 );
      v16 = a4 - 1;
      if ( v13 )
        v16 = a4;
      v11 = v13 == 0 ? 0x8007007A : 0;
      *v16 = 0;
    }
  }
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v9);
  if ( v11 < 0 )
    return (unsigned int)v11;
  result = 0;
  if ( InformationThread < 0 )
    return InformationThread | 0x10000000u;
  return result;
}

```

## disassembly

```asm
0x180024e20  push    rbx
0x180024e22  push    rbp
0x180024e23  push    rsi
0x180024e24  push    rdi
0x180024e25  push    r12
0x180024e27  push    r13
0x180024e29  push    r14
0x180024e2b  push    r15
0x180024e2d  sub     rsp, 48h
0x180024e31  mov     rax, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180024e38  xor     r12d, r12d
0x180024e3b  mov     [rsp+88h+var_58], r12d
0x180024e40  mov     rdi, r9
0x180024e43  mov     rbp, r8
0x180024e46  mov     r13, rcx
0x180024e49  test    rax, rax
0x180024e4c  jz      loc_180024F40
0x180024e52  mov     rcx, [rcx+30h]
0x180024e56  mov     esi, [rsp+88h+arg_20]
0x180024e5d  mov     rax, [rcx]
0x180024e60  lea     r15d, ds:10h[rsi*2]
0x180024e68  mov     edx, r15d
0x180024e6b  mov     rax, [rax+8]
0x180024e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e74  mov     r14, rax
0x180024e77  test    rax, rax
0x180024e7a  jnz     short loc_180024E86
0x180024e7c  mov     eax, 8007000Eh
0x180024e81  jmp     loc_180024F45
0x180024e86  lea     rax, [rsp+88h+var_58]
0x180024e8b  mov     r9, r14; void *
0x180024e8e  mov     [rsp+88h+var_60], rax; unsigned int *
0x180024e93  mov     r8d, 26h ; '&'; enum _THREADINFOCLASS
0x180024e99  mov     rdx, rbp; void *
0x180024e9c  mov     [rsp+88h+var_68], r15d; unsigned int
0x180024ea1  mov     ebx, r12d
0x180024ea4  call    ?NtQueryInformationThread@MiniDumpOsImports@@QEAAJPEAXW4_THREADINFOCLASS@@0KPEAK@Z; MiniDumpOsImports::NtQueryInformationThread(void *,_THREADINFOCLASS,void *,ulong,ulong *)
0x180024ea9  mov     ebp, eax
0x180024eab  test    eax, eax
0x180024ead  js      short loc_180024F15
0x180024eaf  lea     ecx, [rsi-1]
0x180024eb2  mov     rdx, rsi
0x180024eb5  cmp     ecx, 7FFFFFFEh
0x180024ebb  ja      short loc_180024F08
0x180024ebd  movzx   ecx, word ptr [r14]
0x180024ec1  mov     r8, [r14+8]
0x180024ec5  shr     rcx, 1
0x180024ec8  test    rcx, rcx
0x180024ecb  jz      short loc_180024EEA
0x180024ecd  movzx   eax, word ptr [r8]
0x180024ed1  test    ax, ax
0x180024ed4  jz      short loc_180024EEA
0x180024ed6  mov     [rdi], ax
0x180024ed9  add     r8, 2
0x180024edd  add     rdi, 2
0x180024ee1  dec     rcx
0x180024ee4  sub     rdx, 1
0x180024ee8  jnz     short loc_180024EC8
0x180024eea  test    rdx, rdx
0x180024eed  lea     rcx, [rdi-2]
0x180024ef1  cmovnz  rcx, rdi
0x180024ef5  neg     rdx
0x180024ef8  sbb     ebx, ebx
0x180024efa  not     ebx
0x180024efc  and     ebx, 8007007Ah
0x180024f02  mov     [rcx], r12w
0x180024f06  jmp     short loc_180024F15
0x180024f08  mov     ebx, 80070057h
0x180024f0d  test    esi, esi
0x180024f0f  jz      short loc_180024F15
0x180024f11  mov     [rdi], r12w
0x180024f15  mov     rcx, [r13+30h]
0x180024f19  mov     rdx, r14
0x180024f1c  mov     r8, [rcx]
0x180024f1f  mov     rax, [r8+18h]
0x180024f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f28  test    ebx, ebx
0x180024f2a  jns     short loc_180024F30
0x180024f2c  mov     eax, ebx
0x180024f2e  jmp     short loc_180024F45
0x180024f30  mov     ecx, ebp
0x180024f32  mov     eax, r12d
0x180024f35  bts     ecx, 1Ch
0x180024f39  test    ebp, ebp
0x180024f3b  cmovs   eax, ecx
0x180024f3e  jmp     short loc_180024F45
0x180024f40  mov     eax, 80004001h
0x180024f45  add     rsp, 48h
0x180024f49  pop     r15
0x180024f4b  pop     r14
0x180024f4d  pop     r13
0x180024f4f  pop     r12
0x180024f51  pop     rdi
0x180024f52  pop     rsi
0x180024f53  pop     rbp
0x180024f54  pop     rbx
0x180024f55  retn
```
