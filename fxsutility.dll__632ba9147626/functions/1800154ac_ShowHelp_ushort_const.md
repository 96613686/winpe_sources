# ShowHelp(ushort const *)

- ea: `0x1800154ac`
- end: `0x1800155f1`
- name: `?ShowHelp@@YAKPEBG@Z`
- size: `325`
- prototype: `unsigned int __fastcall(OLECHAR *psz)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180011510`
- `0x180012e10`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x1800154ac`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015530`
- `OLEAUT32!__imp_SysAllocString` at `0x180015530`
- `OLEAUT32!__imp_SysFreeString` at `0x18001558f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001558f`
- `ole32!CoInitialize` at `0x1800154fd`
- `ole32!CoInitialize` at `0x1800154fd`
- `ole32!CoUninitialize` at `0x1800155c7`
- `ole32!CoUninitialize` at `0x1800155c7`
- `ole32!CoCreateInstance` at `0x180015521`
- `ole32!CoCreateInstance` at `0x180015521`

## pseudocode

```c
__int64 __fastcall ShowHelp(OLECHAR *psz)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  OLECHAR *v4; // rdi
  int v5; // eax
  __int64 result; // rax
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff530218c81e3c3fbf04fd191574e5b6_Traceguids);
  }
  ppv = 0;
  CoInitialize(0);
  v2 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_ff530218c81e3c3fbf04fd191574e5b6_Traceguids,
        (unsigned int)v2);
    }
  }
  else
  {
    v4 = SysAllocString(psz);
    if ( v4 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 24LL))(ppv, v4);
      v3 = v5;
      if ( v5 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_ff530218c81e3c3fbf04fd191574e5b6_Traceguids,
          (unsigned int)v5);
      }
      SysFreeString(v4);
    }
  }
  CoUninitialize();
  result = (unsigned __int16)v3;
  if ( (v3 & 0x1FFF0000) != 0x70000 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x1800154ac  mov     [rsp+arg_0], rbx
0x1800154b1  mov     [rsp+arg_10], rbp
0x1800154b6  push    rdi
0x1800154b7  sub     rsp, 30h
0x1800154bb  mov     rdi, rcx
0x1800154be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154c5  lea     rbp, WPP_GLOBAL_Control
0x1800154cc  cmp     rcx, rbp
0x1800154cf  jz      short loc_1800154F2
0x1800154d1  test    byte ptr [rcx+1Ch], 2
0x1800154d5  jz      short loc_1800154F2
0x1800154d7  cmp     byte ptr [rcx+19h], 5
0x1800154db  jb      short loc_1800154F2
0x1800154dd  mov     rcx, [rcx+10h]
0x1800154e1  lea     r8, WPP_ff530218c81e3c3fbf04fd191574e5b6_Traceguids
0x1800154e8  mov     edx, 0Ah
0x1800154ed  call    WPP_SF_
0x1800154f2  xor     ecx, ecx; pvReserved
0x1800154f4  mov     [rsp+38h+arg_8], 0
0x1800154fd  call    cs:__imp_CoInitialize
0x180015503  xor     edx, edx; pUnkOuter
0x180015505  lea     rax, [rsp+38h+arg_8]
0x18001550a  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180015511  mov     [rsp+38h+ppv], rax; ppv
0x180015516  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18001551d  lea     r8d, [rdx+1]; dwClsContext
0x180015521  call    cs:__imp_CoCreateInstance
0x180015527  mov     ebx, eax
0x180015529  test    eax, eax
0x18001552b  js      short loc_180015597
0x18001552d  mov     rcx, rdi; psz
0x180015530  call    cs:__imp_SysAllocString
0x180015536  mov     rdi, rax
0x180015539  test    rax, rax
0x18001553c  jz      loc_1800155C7
0x180015542  mov     rcx, [rsp+38h+arg_8]
0x180015547  mov     rdx, [rcx]
0x18001554a  mov     rax, [rdx+18h]
0x18001554e  mov     rdx, rdi
0x180015551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015556  mov     ebx, eax
0x180015558  test    eax, eax
0x18001555a  jns     short loc_18001558C
0x18001555c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015563  cmp     rcx, rbp
0x180015566  jz      short loc_18001558C
0x180015568  test    byte ptr [rcx+1Ch], 2
0x18001556c  jz      short loc_18001558C
0x18001556e  cmp     byte ptr [rcx+19h], 2
0x180015572  jb      short loc_18001558C
0x180015574  mov     rcx, [rcx+10h]
0x180015578  lea     r8, WPP_ff530218c81e3c3fbf04fd191574e5b6_Traceguids
0x18001557f  mov     edx, 0Bh
0x180015584  mov     r9d, eax
0x180015587  call    WPP_SF_d
0x18001558c  mov     rcx, rdi; bstrString
0x18001558f  call    cs:__imp_SysFreeString
0x180015595  jmp     short loc_1800155C7
0x180015597  mov     rcx, cs:WPP_GLOBAL_Control
0x18001559e  cmp     rcx, rbp
0x1800155a1  jz      short loc_1800155C7
0x1800155a3  test    byte ptr [rcx+1Ch], 2
0x1800155a7  jz      short loc_1800155C7
0x1800155a9  cmp     byte ptr [rcx+19h], 2
0x1800155ad  jb      short loc_1800155C7
0x1800155af  mov     rcx, [rcx+10h]
0x1800155b3  lea     r8, WPP_ff530218c81e3c3fbf04fd191574e5b6_Traceguids
0x1800155ba  mov     edx, 0Ch
0x1800155bf  mov     r9d, eax
0x1800155c2  call    WPP_SF_d
0x1800155c7  call    cs:__imp_CoUninitialize
0x1800155cd  mov     rbp, [rsp+38h+arg_10]
0x1800155d2  mov     ecx, ebx
0x1800155d4  movzx   eax, bx
0x1800155d7  and     ecx, 1FFF0000h
0x1800155dd  cmp     ecx, 70000h
0x1800155e3  cmovnz  eax, ebx
0x1800155e6  mov     rbx, [rsp+38h+arg_0]
0x1800155eb  add     rsp, 30h
0x1800155ef  pop     rdi
0x1800155f0  retn
```
