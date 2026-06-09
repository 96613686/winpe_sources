# DwmpGetAnimationClockToken

- ea: `0x180011410`
- end: `0x1800114da`
- name: `DwmpGetAnimationClockToken`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015f90`

## callees

- `0x18000352c`
- `0x18000925c`
- `0x18000d0a0`
- `0x180011410`

## pseudocode

```c
__int64 __fastcall DwmpGetAnimationClockToken(CApiPortClient *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  __int128 v4; // xmm0
  int v5; // eax
  int v7; // [rsp+30h] [rbp-38h] BYREF
  int v8; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+3Ch] [rbp-2Ch]
  __int64 v10; // [rsp+4Ch] [rbp-1Ch]

  if ( a2 )
  {
    v4 = *(_OWORD *)a1;
    *a2 = 0;
    v10 = 0;
    v7 = 0;
    v8 = 1073741927;
    v9 = v4;
    v5 = CApiPortClient::SendRequest(a1, &v8, 28, &v7, &v8, 28);
    v3 = v5;
    if ( v5 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, (const int *const)"W", 3, v5, 0xB8u);
    }
    else
    {
      v3 = v7;
      if ( v7 >= 0 )
        *a2 = v10;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180011410  mov     [rsp+arg_10], rbx
0x180011415  push    rdi
0x180011416  sub     rsp, 60h
0x18001141a  mov     rax, cs:__security_cookie
0x180011421  xor     rax, rsp
0x180011424  mov     [rsp+68h+var_10], rax
0x180011429  mov     rdi, rdx
0x18001142c  test    rdx, rdx
0x18001142f  jnz     short loc_18001143B
0x180011431  mov     ebx, 80070057h
0x180011436  jmp     loc_1800114BD
0x18001143b  movups  xmm0, xmmword ptr [rcx]
0x18001143e  xor     eax, eax
0x180011440  mov     qword ptr [rdx], 0
0x180011447  mov     [rsp+68h+var_1C], rax
0x18001144c  lea     r9, [rsp+68h+var_38]; int *
0x180011451  mov     [rsp+68h+var_38], eax
0x180011455  lea     rdx, [rsp+68h+var_30]; void *
0x18001145a  mov     eax, 1Ch
0x18001145f  mov     [rsp+68h+var_30], 40000067h
0x180011467  mov     word ptr [rsp+68h+var_40], ax; void *
0x18001146c  mov     r8d, eax; __int16
0x18001146f  lea     rax, [rsp+68h+var_30]
0x180011474  mov     [rsp+68h+var_48], rax; void *
0x180011479  movdqu  [rsp+68h+var_2C], xmm0
0x18001147f  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180011484  mov     ebx, eax
0x180011486  test    eax, eax
0x180011488  js      short loc_18001149C
0x18001148a  mov     ebx, [rsp+68h+var_38]
0x18001148e  test    ebx, ebx
0x180011490  js      short loc_1800114BD
0x180011492  mov     rax, [rsp+68h+var_1C]
0x180011497  mov     [rdi], rax
0x18001149a  jmp     short loc_1800114BD
0x18001149c  mov     r8d, 3; unsigned int
0x1800114a2  mov     dword ptr [rsp+68h+var_48], 0B8h; unsigned int
0x1800114aa  mov     r9d, eax; int
0x1800114ad  lea     rdx, aW; "W"
0x1800114b4  lea     ecx, [r8+1]; unsigned int
0x1800114b8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800114bd  mov     eax, ebx
0x1800114bf  mov     rcx, [rsp+68h+var_10]
0x1800114c4  xor     rcx, rsp; StackCookie
0x1800114c7  call    __security_check_cookie
0x1800114cc  mov     rbx, [rsp+68h+arg_10]
0x1800114d4  add     rsp, 60h
0x1800114d8  pop     rdi
0x1800114d9  retn
```
