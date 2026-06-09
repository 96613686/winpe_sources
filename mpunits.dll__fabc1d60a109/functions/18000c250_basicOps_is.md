# basicOps_is

- ea: `0x18000c250`
- end: `0x18000c3a4`
- name: `basicOps_is`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c3b0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000c250`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c279`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000c279`

## string_xrefs

- `0x18000c26e`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_is(__int64 a1, char *a2, __int64 a3)
{
  HMODULE ModuleHandleA; // rax
  __int64 v5; // rbx
  int v6; // ecx
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 v11; // [rsp+30h] [rbp-10h]

  if ( *(_BYTE *)a3 == 0xFC )
  {
    v5 = 0;
    if ( (*(_DWORD *)a2 & 0x100) != 0 )
    {
      *(_OWORD *)a1 = 0u;
      return a1;
    }
    v6 = *(_DWORD *)(a3 + 8);
    v7 = *a2;
    switch ( v6 )
    {
      case -1003:
        if ( (_BYTE)v7 == 15 )
          v9 = ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL));
        else
          v9 = 0;
        *(_QWORD *)&v11 = 0;
        LOBYTE(v5) = v9 != 0;
        goto LABEL_20;
      case -1002:
        if ( (_BYTE)v7 == 12 )
        {
          v8 = 1;
          if ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
            goto LABEL_12;
        }
        break;
      case -1001:
        if ( (_BYTE)v7 == 12 )
        {
          v8 = 1;
          if ( !*(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
          {
LABEL_12:
            *(_QWORD *)&v11 = 0;
            *((_QWORD *)&v11 + 1) = v8;
LABEL_21:
            *(_OWORD *)a1 = v11;
            return a1;
          }
        }
        break;
      default:
        *(_QWORD *)&v11 = 0;
        LOBYTE(v5) = v7 == v6;
LABEL_20:
        *((_QWORD *)&v11 + 1) = v5;
        goto LABEL_21;
    }
    v8 = 0;
    goto LABEL_12;
  }
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_GetString_LoadString(ModuleHandleA, 2093);
  MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x18000c250  mov     [rsp-8+arg_0], rbx
0x18000c255  mov     [rsp-8+arg_8], rdi
0x18000c25a  push    rbp
0x18000c25b  mov     rbp, rsp
0x18000c25e  sub     rsp, 40h
0x18000c262  cmp     byte ptr [r8], 0FCh
0x18000c266  mov     rdi, rcx
0x18000c269  jz      short loc_18000C2DE
0x18000c26b  xorps   xmm0, xmm0
0x18000c26e  lea     rcx, ModuleName; "mpunits.dll"
0x18000c275  movups  [rbp+var_10], xmm0
0x18000c279  call    cs:__imp_GetModuleHandleA
0x18000c27f  mov     rcx, rax
0x18000c282  mov     edx, 82Dh
0x18000c287  call    _Intlstr_GetString_LoadString
0x18000c28c  xor     ebx, ebx
0x18000c28e  mov     qword ptr [rbp+var_10], rax
0x18000c292  mov     byte ptr [rbp+var_10+8], bl
0x18000c295  lea     r9, [rbp+var_10]
0x18000c299  movaps  xmm0, [rbp+var_10]
0x18000c29d  lea     rdx, aMi; "MI"
0x18000c2a4  mov     [rsp+40h+var_18], rbx; __int64
0x18000c2a9  lea     r8d, [rbx+5]
0x18000c2ad  movdqa  [rbp+var_10], xmm0
0x18000c2b2  lea     ecx, [rbx+4]; int
0x18000c2b5  mov     [rsp+40h+var_20], rbx; __int64
0x18000c2ba  call    MI_ReportErrorDetails_ForCustomError
0x18000c2bf  xor     edx, edx
0x18000c2c1  xor     ecx, ecx
0x18000c2c3  mov     eax, 0FFh
0x18000c2c8  mov     [rdi+4], edx
0x18000c2cb  and     eax, 0FFFFFFFEh
0x18000c2ce  mov     [rdi+8], rcx
0x18000c2d2  or      eax, 0FEh
0x18000c2d7  mov     [rdi], eax
0x18000c2d9  jmp     loc_18000C391
0x18000c2de  xor     ebx, ebx
0x18000c2e0  test    dword ptr [rdx], 100h
0x18000c2e6  jz      short loc_18000C2FD
0x18000c2e8  mov     qword ptr [rbp+var_10], rbx
0x18000c2ec  mov     qword ptr [rbp+var_10+8], rbx
0x18000c2f0  movups  xmm0, [rbp+var_10]
0x18000c2f4  movdqu  xmmword ptr [rcx], xmm0
0x18000c2f8  jmp     loc_18000C391
0x18000c2fd  mov     ecx, [r8+8]
0x18000c301  movsx   eax, byte ptr [rdx]
0x18000c304  cmp     ecx, 0FFFFFC15h
0x18000c30a  jz      short loc_18000C35A
0x18000c30c  cmp     ecx, 0FFFFFC16h
0x18000c312  jz      short loc_18000C346
0x18000c314  cmp     ecx, 0FFFFFC17h
0x18000c31a  jz      short loc_18000C327
0x18000c31c  cmp     eax, ecx
0x18000c31e  mov     qword ptr [rbp+var_10], rbx
0x18000c322  setz    bl
0x18000c325  jmp     short loc_18000C385
0x18000c327  cmp     al, 0Ch
0x18000c329  jnz     short loc_18000C339
0x18000c32b  mov     rax, [rdx+8]
0x18000c32f  cmp     [rax+10h], ebx
0x18000c332  mov     eax, 1
0x18000c337  jz      short loc_18000C33C
0x18000c339  mov     rax, rbx
0x18000c33c  mov     qword ptr [rbp+var_10], rbx
0x18000c340  mov     qword ptr [rbp+var_10+8], rax
0x18000c344  jmp     short loc_18000C389
0x18000c346  cmp     al, 0Ch
0x18000c348  jnz     short loc_18000C339
0x18000c34a  mov     rax, [rdx+8]
0x18000c34e  cmp     [rax+10h], ebx
0x18000c351  mov     eax, 1
0x18000c356  jnz     short loc_18000C33C
0x18000c358  jmp     short loc_18000C339
0x18000c35a  cmp     al, 0Fh
0x18000c35c  jnz     short loc_18000C378
0x18000c35e  mov     rcx, [rdx+8]
0x18000c362  mov     rax, cs:off_180047B90
0x18000c369  mov     rcx, [rcx+18h]
0x18000c36d  mov     rax, [rax+8]
0x18000c371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c376  jmp     short loc_18000C37B
0x18000c378  mov     rax, rbx
0x18000c37b  test    rax, rax
0x18000c37e  mov     qword ptr [rbp+var_10], rbx
0x18000c382  setnz   bl
0x18000c385  mov     qword ptr [rbp+var_10+8], rbx
0x18000c389  movups  xmm0, [rbp+var_10]
0x18000c38d  movdqu  xmmword ptr [rdi], xmm0
0x18000c391  mov     rbx, [rsp+40h+arg_0]
0x18000c396  mov     rax, rdi
0x18000c399  mov     rdi, [rsp+40h+arg_8]
0x18000c39e  add     rsp, 40h
0x18000c3a2  pop     rbp
0x18000c3a3  retn
```
