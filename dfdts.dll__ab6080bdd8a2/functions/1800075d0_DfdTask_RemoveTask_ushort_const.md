# DfdTask::RemoveTask(ushort const *)

- ea: `0x1800075d0`
- end: `0x180007712`
- name: `?RemoveTask@DfdTask@@QEAAJPEBG@Z`
- size: `322`
- prototype: `__int64 __fastcall(DfdTask *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000357c`

## callees

- `0x180002c68`
- `0x180003984`
- `0x1800075d0`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007608`
- `OLEAUT32!__imp_SysAllocString` at `0x180007608`
- `OLEAUT32!__imp_SysFreeString` at `0x180007700`
- `OLEAUT32!__imp_SysFreeString` at `0x180007700`

## pseudocode

```c
__int64 __fastcall DfdTask::RemoveTask(DfdTask *this, const unsigned __int16 *a2)
{
  bool v2; // zf
  int v3; // esi
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  int v7; // ebx
  int v8; // eax
  _QWORD *v9; // rcx
  int v10; // eax
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this == 0;
  v3 = (int)a2;
  v12 = 0;
  if ( v2 || !*((_QWORD *)this + 2) )
  {
    v6 = 0;
    v7 = -2147467259;
  }
  else
  {
    v5 = SysAllocString(a2);
    v6 = v5;
    if ( v5 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**((_QWORD **)this + 2) + 104LL))(
             *((_QWORD *)this + 2),
             v5,
             &v12);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 88LL))(v12, 0);
        v9 = WPP_GLOBAL_Control;
        v7 = v10;
      }
      else
      {
        if ( (unsigned int)(unsigned __int16)v8 - 2 > 1 && (unsigned __int16)v8 != 1168 )
          goto LABEL_16;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4f3495666d7e372198f3636e22490d50_Traceguids);
          v9 = WPP_GLOBAL_Control;
        }
        v7 = 0;
      }
      if ( v7 >= 0 )
        goto LABEL_20;
      goto LABEL_17;
    }
    v7 = -2147024882;
  }
LABEL_16:
  v9 = WPP_GLOBAL_Control;
LABEL_17:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
    WPP_SF_Sd(v9[2], 21, (unsigned int)WPP_4f3495666d7e372198f3636e22490d50_Traceguids, v3, v7);
LABEL_20:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v6 )
    SysFreeString(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800075d0  push    rbx
0x1800075d2  push    rsi
0x1800075d3  push    rdi
0x1800075d4  push    r14
0x1800075d6  sub     rsp, 38h
0x1800075da  cmp     qword ptr [rcx], 0
0x1800075de  lea     r14, WPP_GLOBAL_Control
0x1800075e5  mov     rsi, rdx
0x1800075e8  mov     [rsp+58h+arg_0], 0
0x1800075f1  mov     rbx, rcx
0x1800075f4  jz      loc_1800076A4
0x1800075fa  cmp     qword ptr [rcx+10h], 0
0x1800075ff  jz      loc_1800076A4
0x180007605  mov     rcx, rdx; psz
0x180007608  call    cs:__imp_SysAllocString
0x18000760e  mov     rdi, rax
0x180007611  test    rax, rax
0x180007614  jnz     short loc_180007620
0x180007616  mov     ebx, 8007000Eh
0x18000761b  jmp     loc_1800076AB
0x180007620  mov     rcx, [rbx+10h]
0x180007624  lea     r8, [rsp+58h+arg_0]
0x180007629  mov     rdx, rdi
0x18000762c  mov     rax, [rcx]
0x18000762f  mov     rax, [rax+68h]
0x180007633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007638  mov     ebx, eax
0x18000763a  test    eax, eax
0x18000763c  jns     short loc_180007682
0x18000763e  movzx   eax, ax
0x180007641  lea     ecx, [rax-2]
0x180007644  cmp     ecx, 1
0x180007647  jbe     short loc_180007650
0x180007649  cmp     eax, 490h
0x18000764e  jnz     short loc_1800076AB
0x180007650  mov     rcx, cs:WPP_GLOBAL_Control
0x180007657  cmp     rcx, r14
0x18000765a  jz      short loc_18000767E
0x18000765c  test    byte ptr [rcx+1Ch], 4
0x180007660  jz      short loc_18000767E
0x180007662  mov     rcx, [rcx+10h]
0x180007666  lea     r8, WPP_4f3495666d7e372198f3636e22490d50_Traceguids
0x18000766d  mov     edx, 14h
0x180007672  call    WPP_SF_
0x180007677  mov     rcx, cs:WPP_GLOBAL_Control
0x18000767e  xor     ebx, ebx
0x180007680  jmp     short loc_18000769E
0x180007682  mov     rcx, [rsp+58h+arg_0]
0x180007687  xor     edx, edx
0x180007689  mov     rax, [rcx]
0x18000768c  mov     rax, [rax+58h]
0x180007690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007695  mov     rcx, cs:WPP_GLOBAL_Control
0x18000769c  mov     ebx, eax
0x18000769e  test    ebx, ebx
0x1800076a0  js      short loc_1800076B2
0x1800076a2  jmp     short loc_1800076D9
0x1800076a4  xor     edi, edi
0x1800076a6  mov     ebx, 80004005h
0x1800076ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076b2  cmp     rcx, r14
0x1800076b5  jz      short loc_1800076D9
0x1800076b7  test    byte ptr [rcx+1Ch], 1
0x1800076bb  jz      short loc_1800076D9
0x1800076bd  mov     rcx, [rcx+10h]
0x1800076c1  lea     r8, WPP_4f3495666d7e372198f3636e22490d50_Traceguids
0x1800076c8  mov     edx, 15h
0x1800076cd  mov     [rsp+58h+var_38], ebx
0x1800076d1  mov     r9, rsi
0x1800076d4  call    WPP_SF_Sd
0x1800076d9  mov     rcx, [rsp+58h+arg_0]
0x1800076de  test    rcx, rcx
0x1800076e1  jz      short loc_1800076F8
0x1800076e3  mov     rax, [rcx]
0x1800076e6  mov     rax, [rax+10h]
0x1800076ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ef  mov     [rsp+58h+arg_0], 0
0x1800076f8  test    rdi, rdi
0x1800076fb  jz      short loc_180007706
0x1800076fd  mov     rcx, rdi; bstrString
0x180007700  call    cs:__imp_SysFreeString
0x180007706  mov     eax, ebx
0x180007708  add     rsp, 38h
0x18000770c  pop     r14
0x18000770e  pop     rdi
0x18000770f  pop     rsi
0x180007710  pop     rbx
0x180007711  retn
```
