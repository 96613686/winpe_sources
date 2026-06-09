# CRegNode::MoveToParentKeyOfKey(void)

- ea: `0x180054570`
- end: `0x1800546cb`
- name: `?MoveToParentKeyOfKey@CRegNode@@UEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(CRegNode *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a01c`
- `0x1800540b4`
- `0x180054570`
- `0x1800546f8`
- `0x180055550`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180054632`
- `msvcrt!wcsrchr` at `0x180054632`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800545e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800545e4`

## pseudocode

```c
__int64 __fastcall CRegNode::MoveToParentKeyOfKey(CRegNode *this)
{
  HKEY v1; // r12
  unsigned __int16 *v3; // rdi
  __int64 v4; // r13
  int v5; // r15d
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned __int16 *v8; // r14
  unsigned __int16 *p_Str; // rsi
  unsigned __int16 *v10; // rax
  int v12; // ebp
  __int64 v13; // r11
  wchar_t *v14; // rax
  wchar_t Str; // [rsp+20h] [rbp-828h] BYREF

  v1 = (HKEY)*((_QWORD *)this + 3);
  v3 = (unsigned __int16 *)*((_QWORD *)this + 4);
  v4 = *((_QWORD *)this + 5);
  v5 = *((_DWORD *)this + 20);
  v6 = -1;
  do
    ++v6;
  while ( v3[v6] );
  v7 = 1000;
  if ( v6 >= 0x3E8 )
  {
    v7 = v6 + 1;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v6 + 1, 2u));
    p_Str = v10;
    if ( !v10 )
      return 2147942414LL;
    v8 = v10;
  }
  else
  {
    v8 = 0;
    p_Str = &Str;
  }
  v12 = StringCchCopyW(p_Str, v7, v3);
  if ( v12 >= 0 )
  {
    *((_QWORD *)this + 3) = *((_QWORD *)this + 2);
    *((_QWORD *)this + 4) = v13;
    *((_QWORD *)this + 5) = v13;
    *((_DWORD *)this + 20) = v13;
    v14 = wcsrchr(p_Str, 0x5Cu);
    if ( v14 )
      *v14 = 0;
    v12 = CRegNode::MoveToDescendantOr(this, 0, p_Str, L"\\");
    v13 = 0;
  }
  if ( v8 )
  {
    CoTaskMemFree(p_Str);
    v13 = 0;
  }
  if ( v12 < 0 )
  {
    *((_QWORD *)this + 3) = v1;
    *((_QWORD *)this + 4) = v3;
    *((_QWORD *)this + 5) = v4;
    *((_DWORD *)this + 20) = v5;
  }
  else
  {
    if ( *((_QWORD *)this + 9) == v13 )
    {
      RegSafeCloseKey(v1);
LABEL_17:
      if ( v3 )
        CoTaskMemFree(v3);
      return (unsigned int)v12;
    }
    if ( v5 )
      goto LABEL_17;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180054570  push    rbx
0x180054572  push    rbp
0x180054573  push    rsi
0x180054574  push    rdi
0x180054575  push    r12
0x180054577  push    r13
0x180054579  push    r14
0x18005457b  push    r15
0x18005457d  sub     rsp, 808h
0x180054584  mov     rax, cs:__security_cookie
0x18005458b  xor     rax, rsp
0x18005458e  mov     [rsp+848h+var_58], rax
0x180054596  mov     r12, [rcx+18h]
0x18005459a  mov     rbx, rcx
0x18005459d  mov     rdi, [rcx+20h]
0x1800545a1  mov     r13, [rcx+28h]
0x1800545a5  mov     r15d, [rcx+50h]
0x1800545a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800545ad  mov     rax, rcx
0x1800545b0  xor     r11d, r11d
0x1800545b3  inc     rax
0x1800545b6  cmp     [rdi+rax*2], r11w
0x1800545bb  jnz     short loc_1800545B3
0x1800545bd  mov     ebp, 3E8h
0x1800545c2  cmp     rax, rbp
0x1800545c5  jnb     short loc_1800545D1
0x1800545c7  mov     r14, r11
0x1800545ca  lea     rsi, [rsp+848h+Str]
0x1800545cf  jmp     short loc_180054602
0x1800545d1  lea     rbp, [rax+1]
0x1800545d5  mov     eax, 2
0x1800545da  mul     rbp
0x1800545dd  cmovb   rax, rcx
0x1800545e1  mov     rcx, rax; cb
0x1800545e4  call    cs:__imp_CoTaskMemAlloc
0x1800545ea  xor     r11d, r11d
0x1800545ed  mov     rsi, rax
0x1800545f0  test    rax, rax
0x1800545f3  jnz     short loc_1800545FF
0x1800545f5  mov     eax, 8007000Eh
0x1800545fa  jmp     loc_1800546A7
0x1800545ff  mov     r14, rax
0x180054602  mov     r8, rdi; unsigned __int16 *
0x180054605  mov     rdx, rbp; unsigned __int64
0x180054608  mov     rcx, rsi; unsigned __int16 *
0x18005460b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054610  mov     ebp, eax
0x180054612  test    eax, eax
0x180054614  js      short loc_18005465B
0x180054616  mov     rax, [rbx+10h]
0x18005461a  mov     edx, 5Ch ; '\'; Ch
0x18005461f  mov     rcx, rsi; Str
0x180054622  mov     [rbx+18h], rax
0x180054626  mov     [rbx+20h], r11
0x18005462a  mov     [rbx+28h], r11
0x18005462e  mov     [rbx+50h], r11d
0x180054632  call    cs:__imp_wcsrchr
0x180054638  test    rax, rax
0x18005463b  jz      short loc_180054642
0x18005463d  xor     ecx, ecx
0x18005463f  mov     [rax], cx
0x180054642  lea     r9, asc_18005D30C; "\\"
0x180054649  mov     r8, rsi; unsigned __int16 *
0x18005464c  xor     edx, edx; unsigned int
0x18005464e  mov     rcx, rbx; this
0x180054651  call    ?MoveToDescendantOr@CRegNode@@AEAAJKPEBG0@Z; CRegNode::MoveToDescendantOr(ulong,ushort const *,ushort const *)
0x180054656  mov     ebp, eax
0x180054658  xor     r11d, r11d
0x18005465b  test    r14, r14
0x18005465e  jz      short loc_18005466C
0x180054660  mov     rcx, rsi; pv
0x180054663  call    cs:__imp_CoTaskMemFree
0x180054669  xor     r11d, r11d
0x18005466c  test    ebp, ebp
0x18005466e  js      short loc_180054695
0x180054670  cmp     [rbx+48h], r11
0x180054674  jz      short loc_18005468B
0x180054676  test    r15d, r15d
0x180054679  jz      short loc_1800546A5
0x18005467b  test    rdi, rdi
0x18005467e  jz      short loc_1800546A5
0x180054680  mov     rcx, rdi; pv
0x180054683  call    cs:__imp_CoTaskMemFree
0x180054689  jmp     short loc_1800546A5
0x18005468b  mov     rcx, r12; HKEY
0x18005468e  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180054693  jmp     short loc_18005467B
0x180054695  mov     [rbx+18h], r12
0x180054699  mov     [rbx+20h], rdi
0x18005469d  mov     [rbx+28h], r13
0x1800546a1  mov     [rbx+50h], r15d
0x1800546a5  mov     eax, ebp
0x1800546a7  mov     rcx, [rsp+848h+var_58]
0x1800546af  xor     rcx, rsp; StackCookie
0x1800546b2  call    __security_check_cookie
0x1800546b7  add     rsp, 808h
0x1800546be  pop     r15
0x1800546c0  pop     r14
0x1800546c2  pop     r13
0x1800546c4  pop     r12
0x1800546c6  pop     rdi
0x1800546c7  pop     rsi
0x1800546c8  pop     rbp
0x1800546c9  pop     rbx
0x1800546ca  retn
```
