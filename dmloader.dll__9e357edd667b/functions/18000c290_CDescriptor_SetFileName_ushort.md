# CDescriptor::SetFileName(ushort *)

- ea: `0x18000c290`
- end: `0x18000c3e9`
- name: `?SetFileName@CDescriptor@@QEAAJPEAG@Z`
- size: `345`
- prototype: `__int64 __fastcall(CDescriptor *__hidden this, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a484`
- `0x18000b358`
- `0x18000bbc4`
- `0x18000c018`
- `0x18000c5d8`

## callees

- `0x1800015d0`
- `0x1800019a0`
- `0x1800019ac`
- `0x180001ef0`
- `0x180006cac`
- `0x18000c290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c33d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c33d`

## pseudocode

```c
__int64 __fastcall CDescriptor::SetFileName(CDescriptor *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rdi
  __int64 result; // rax
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  unsigned int v14; // edx
  unsigned __int16 v15; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v16[526]; // [rsp+22h] [rbp-226h] BYREF

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  v15 = 0;
  memset_0(v16, 0, 0x206u);
  v5 = 2147483646;
  v6 = &v15;
  v7 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*v2 )
      break;
    *v6++ = *v2++;
    --v5;
    --v7;
  }
  while ( v7 );
  v8 = v6 - 1;
  if ( v7 )
    v8 = v6;
  *v8 = 0;
  if ( !v7 )
    return 2147942487LL;
  v9 = *((_QWORD *)this + 10);
  if ( v9 && !(unsigned int)_o__wcsicmp(v9, &v15) )
    return 1;
  v10 = (void *)*((_QWORD *)this + 10);
  if ( v10 )
    operator delete(v10);
  *((_DWORD *)this + 2) &= ~0x10u;
  *((_QWORD *)this + 10) = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&v16[2 * v11 - 2] );
  v12 = v11 + 1;
  v13 = (unsigned __int16 *)operator new[](saturated_mul(v11 + 1, 2u));
  *((_QWORD *)this + 10) = v13;
  if ( v13 )
    result = StringCchCopyW(v13, v12, &v15);
  else
    result = 2147942414LL;
  v14 = *((_DWORD *)this + 2) | 0x10;
  if ( (int)result < 0 )
    v14 = *((_DWORD *)this + 2) & 0xFFFFFFEF;
  *((_DWORD *)this + 2) = v14;
  return result;
}

```

## disassembly

```asm
0x18000c290  mov     [rsp+arg_8], rbx
0x18000c295  mov     [rsp+arg_10], rsi
0x18000c29a  push    rdi
0x18000c29b  sub     rsp, 240h
0x18000c2a2  mov     rax, cs:__security_cookie
0x18000c2a9  xor     rax, rsp
0x18000c2ac  mov     [rsp+248h+var_18], rax
0x18000c2b4  xor     esi, esi
0x18000c2b6  mov     rdi, rdx
0x18000c2b9  mov     rbx, rcx
0x18000c2bc  test    rdx, rdx
0x18000c2bf  jnz     short loc_18000C2CB
0x18000c2c1  mov     eax, 80004003h
0x18000c2c6  jmp     loc_18000C3C4
0x18000c2cb  xor     edx, edx; Val
0x18000c2cd  mov     [rsp+248h+var_228], si
0x18000c2d2  mov     r8d, 206h; Size
0x18000c2d8  lea     rcx, [rsp+248h+var_226]; void *
0x18000c2dd  call    memset_0
0x18000c2e2  mov     ecx, 7FFFFFFEh
0x18000c2e7  lea     rax, [rsp+248h+var_228]
0x18000c2ec  mov     edx, 104h
0x18000c2f1  test    rcx, rcx
0x18000c2f4  jz      short loc_18000C315
0x18000c2f6  movzx   r8d, word ptr [rdi]
0x18000c2fa  test    r8w, r8w
0x18000c2fe  jz      short loc_18000C315
0x18000c300  mov     [rax], r8w
0x18000c304  add     rdi, 2
0x18000c308  add     rax, 2
0x18000c30c  dec     rcx
0x18000c30f  sub     rdx, 1; unsigned __int64
0x18000c313  jnz     short loc_18000C2F1
0x18000c315  test    rdx, rdx
0x18000c318  lea     rcx, [rax-2]
0x18000c31c  cmovnz  rcx, rax
0x18000c320  mov     [rcx], si
0x18000c323  jnz     short loc_18000C32F
0x18000c325  mov     eax, 80070057h
0x18000c32a  jmp     loc_18000C3C4
0x18000c32f  mov     rcx, [rbx+50h]
0x18000c333  test    rcx, rcx
0x18000c336  jz      short loc_18000C34E
0x18000c338  lea     rdx, [rsp+248h+var_228]
0x18000c33d  call    cs:__imp__o__wcsicmp
0x18000c343  test    eax, eax
0x18000c345  jnz     short loc_18000C34E
0x18000c347  mov     eax, 1
0x18000c34c  jmp     short loc_18000C3C4
0x18000c34e  mov     rcx, [rbx+50h]; void *
0x18000c352  test    rcx, rcx
0x18000c355  jz      short loc_18000C35C
0x18000c357  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c35c  and     dword ptr [rbx+8], 0FFFFFFEFh
0x18000c360  lea     rax, [rsp+248h+var_228]
0x18000c365  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c369  mov     [rbx+50h], rsi
0x18000c36d  mov     rcx, r8
0x18000c370  inc     rcx
0x18000c373  cmp     [rax+rcx*2], si
0x18000c377  jnz     short loc_18000C370
0x18000c379  lea     rdi, [rcx+1]
0x18000c37d  mov     eax, 2
0x18000c382  mul     rdi
0x18000c385  cmovb   rax, r8
0x18000c389  mov     rcx, rax; unsigned __int64
0x18000c38c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c391  mov     [rbx+50h], rax
0x18000c395  test    rax, rax
0x18000c398  jnz     short loc_18000C3A1
0x18000c39a  mov     eax, 8007000Eh
0x18000c39f  jmp     short loc_18000C3B1
0x18000c3a1  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x18000c3a6  mov     rdx, rdi; unsigned __int64
0x18000c3a9  mov     rcx, rax; unsigned __int16 *
0x18000c3ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c3b1  mov     edx, [rbx+8]
0x18000c3b4  mov     ecx, edx
0x18000c3b6  and     ecx, 0FFFFFFEFh
0x18000c3b9  or      edx, 10h
0x18000c3bc  test    eax, eax
0x18000c3be  cmovs   edx, ecx
0x18000c3c1  mov     [rbx+8], edx
0x18000c3c4  mov     rcx, [rsp+248h+var_18]
0x18000c3cc  xor     rcx, rsp; StackCookie
0x18000c3cf  call    __security_check_cookie
0x18000c3d4  lea     r11, [rsp+248h+var_8]
0x18000c3dc  mov     rbx, [r11+18h]
0x18000c3e0  mov     rsi, [r11+20h]
0x18000c3e4  mov     rsp, r11
0x18000c3e7  pop     rdi
0x18000c3e8  retn
```
