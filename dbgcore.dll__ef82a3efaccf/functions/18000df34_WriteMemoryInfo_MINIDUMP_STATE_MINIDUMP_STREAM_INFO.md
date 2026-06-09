# WriteMemoryInfo(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)

- ea: `0x18000df34`
- end: `0x18000e113`
- name: `?WriteMemoryInfo@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x18000bcbc`
- `0x18000df34`
- `0x18001951c`
- `0x18002c010`

## string_xrefs

- `0x18000e0b7`: `WriteMemoryInfo.QueryVirtual(0x%I64x) failed, 0x%08x`
- `0x18000e05c`: `WriteMemoryInfo.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteMemoryInfo(struct _MINIDUMP_STATE *a1, struct _MINIDUMP_STREAM_INFO *a2)
{
  unsigned int v5; // edx
  unsigned int v6; // ebx
  __int64 i; // r14
  __int64 v8; // rcx
  __int64 v9; // r9
  const char *v10; // r8
  __int64 v11; // rax
  _DWORD v12[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-48h]
  __int128 v14; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h]
  __int128 v16; // [rsp+60h] [rbp-20h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( *((_QWORD *)a2 + 20) <= 0xFFFFFFFF )
  {
    v5 = *((_DWORD *)a2 + 40);
    *((_DWORD *)a2 + 42) = v5;
    v12[0] = 16;
    v12[1] = 48;
    v13 = 0;
    v6 = WriteAtOffset(a1, v5, v12, 0x10u);
    if ( !v6 )
    {
      for ( i = 0; ; i = v14 + *((_QWORD *)&v15 + 1) )
      {
        if ( (unsigned int)GenCheckCancel(a1) )
          return 2147943623LL;
        v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int128 *))(**((_QWORD **)a1 + 2) + 248LL))(
               *((_QWORD *)a1 + 2),
               *(_QWORD *)a1,
               i,
               &v14);
        if ( v6 )
          break;
        if ( v13 >= 0x5555554 )
        {
          v6 = -2147024809;
          (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            4,
            "Memory info stream overflowed");
          return v6;
        }
        v8 = *((_QWORD *)a1 + 3);
        ++v13;
        v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, &v14, v6 + 48);
        if ( v6 )
        {
          v9 = 48;
          v10 = "WriteMemoryInfo.Write(0x%x) failed, 0x%08x";
LABEL_16:
          (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            4,
            v10,
            v9,
            v6);
          return v6;
        }
      }
      if ( v6 != -2147467262 )
      {
        v9 = i;
        v10 = "WriteMemoryInfo.QueryVirtual(0x%I64x) failed, 0x%08x";
        goto LABEL_16;
      }
      v11 = (unsigned int)(48 * v13 + 16);
      *((_QWORD *)a2 + 20) += v11;
      *((_DWORD *)a2 + 43) = v11;
      return (unsigned int)WriteAtOffset(a1, *((_DWORD *)a2 + 42), v12, 0x10u);
    }
    return v6;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "Memory info stream RVA overflowed");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000df34  mov     [rsp-18h+arg_10], rbx
0x18000df39  mov     [rsp-18h+arg_18], rsi
0x18000df3e  push    rbp
0x18000df3f  push    rdi
0x18000df40  push    r14
0x18000df42  mov     rbp, rsp
0x18000df45  sub     rsp, 80h
0x18000df4c  mov     rax, cs:__security_cookie
0x18000df53  xor     rax, rsp
0x18000df56  mov     [rbp+var_10], rax
0x18000df5a  xorps   xmm0, xmm0
0x18000df5d  mov     eax, 0FFFFFFFFh
0x18000df62  mov     rsi, rdx
0x18000df65  mov     rdi, rcx
0x18000df68  movups  [rbp+var_40], xmm0
0x18000df6c  movups  [rbp+var_30], xmm0
0x18000df70  movups  [rbp+var_20], xmm0
0x18000df74  cmp     [rdx+0A0h], rax
0x18000df7b  jbe     short loc_18000DFA3
0x18000df7d  mov     rcx, [rcx+28h]
0x18000df81  lea     r8, aMemoryInfoStre_0; "Memory info stream RVA overflowed"
0x18000df88  mov     edx, 4
0x18000df8d  mov     rax, [rcx]
0x18000df90  mov     rax, [rax+8]
0x18000df94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df99  mov     eax, 80070057h
0x18000df9e  jmp     loc_18000E088
0x18000dfa3  mov     edx, [rdx+0A0h]; unsigned int
0x18000dfa9  lea     r8, [rbp+var_50]; void *
0x18000dfad  mov     r9d, 10h; unsigned int
0x18000dfb3  mov     [rsi+0A8h], edx
0x18000dfb9  mov     [rbp+var_50], 10h
0x18000dfc0  mov     [rbp+var_4C], 30h ; '0'
0x18000dfc7  mov     [rbp+var_48], 0
0x18000dfcf  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000dfd4  mov     ebx, eax
0x18000dfd6  test    eax, eax
0x18000dfd8  jnz     loc_18000E086
0x18000dfde  xor     r14d, r14d
0x18000dfe1  jmp     short loc_18000E043
0x18000dfe3  mov     rcx, [rdi+10h]
0x18000dfe7  lea     r9, [rbp+var_40]
0x18000dfeb  mov     rdx, [rdi]
0x18000dfee  mov     r8, r14
0x18000dff1  mov     rax, [rcx]
0x18000dff4  mov     rax, [rax+0F8h]
0x18000dffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e000  mov     ebx, eax
0x18000e002  test    eax, eax
0x18000e004  jnz     loc_18000E0AC
0x18000e00a  mov     rax, [rbp+var_48]
0x18000e00e  cmp     rax, 5555554h
0x18000e014  jnb     short loc_18000E065
0x18000e016  mov     rcx, [rdi+18h]
0x18000e01a  lea     r8d, [rbx+30h]
0x18000e01e  inc     rax
0x18000e021  lea     rdx, [rbp+var_40]
0x18000e025  mov     [rbp+var_48], rax
0x18000e029  mov     rax, [rcx]
0x18000e02c  mov     rax, [rax+20h]
0x18000e030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e035  mov     ebx, eax
0x18000e037  test    eax, eax
0x18000e039  jnz     short loc_18000E056
0x18000e03b  mov     r14, qword ptr [rbp+var_30+8]
0x18000e03f  add     r14, qword ptr [rbp+var_40]
0x18000e043  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000e046  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000e04b  test    eax, eax
0x18000e04d  jz      short loc_18000DFE3
0x18000e04f  mov     eax, 800704C7h
0x18000e054  jmp     short loc_18000E088
0x18000e056  mov     r9d, 30h ; '0'
0x18000e05c  lea     r8, aWritememoryinf_0; "WriteMemoryInfo.Write(0x%x) failed, 0x%"...
0x18000e063  jmp     short loc_18000E0BE
0x18000e065  mov     rcx, [rdi+28h]
0x18000e069  lea     r8, aMemoryInfoStre; "Memory info stream overflowed"
0x18000e070  mov     edx, 4
0x18000e075  mov     ebx, 80070057h
0x18000e07a  mov     rax, [rcx]
0x18000e07d  mov     rax, [rax+8]
0x18000e081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e086  mov     eax, ebx
0x18000e088  mov     rcx, [rbp+var_10]
0x18000e08c  xor     rcx, rsp; StackCookie
0x18000e08f  call    __security_check_cookie
0x18000e094  lea     r11, [rsp+80h+var_s0]
0x18000e09c  mov     rbx, [r11+30h]
0x18000e0a0  mov     rsi, [r11+38h]
0x18000e0a4  mov     rsp, r11
0x18000e0a7  pop     r14
0x18000e0a9  pop     rdi
0x18000e0aa  pop     rbp
0x18000e0ab  retn
0x18000e0ac  cmp     ebx, 80004002h
0x18000e0b2  jz      short loc_18000E0D9
0x18000e0b4  mov     r9, r14
0x18000e0b7  lea     r8, aWritememoryinf; "WriteMemoryInfo.QueryVirtual(0x%I64x) f"...
0x18000e0be  mov     rcx, [rdi+28h]
0x18000e0c2  mov     edx, 4
0x18000e0c7  mov     [rsp+80h+var_60], ebx
0x18000e0cb  mov     rax, [rcx]
0x18000e0ce  mov     rax, [rax+8]
0x18000e0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d7  jmp     short loc_18000E086
0x18000e0d9  mov     eax, dword ptr [rbp+var_48]
0x18000e0dc  lea     r8, [rbp+var_50]; void *
0x18000e0e0  mov     r9d, 10h; unsigned int
0x18000e0e6  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000e0e9  lea     edx, [rax+rax*2]
0x18000e0ec  shl     edx, 4
0x18000e0ef  add     edx, 10h
0x18000e0f2  mov     eax, edx
0x18000e0f4  add     [rsi+0A0h], rax
0x18000e0fb  mov     [rsi+0ACh], edx
0x18000e101  mov     edx, [rsi+0A8h]; unsigned int
0x18000e107  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000e10c  mov     ebx, eax
0x18000e10e  jmp     loc_18000E086
```
