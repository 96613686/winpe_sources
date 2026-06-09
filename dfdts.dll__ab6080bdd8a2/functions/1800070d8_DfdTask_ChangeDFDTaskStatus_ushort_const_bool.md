# DfdTask::ChangeDFDTaskStatus(ushort const *,bool)

- ea: `0x1800070d8`
- end: `0x18000733a`
- name: `?ChangeDFDTaskStatus@DfdTask@@QEAAJPEBG_N@Z`
- size: `610`
- prototype: `__int64 __fastcall(DfdTask *this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000357c`

## callees

- `0x180002c90`
- `0x180003924`
- `0x1800070d8`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007131`
- `OLEAUT32!__imp_SysAllocString` at `0x180007131`
- `OLEAUT32!__imp_SysFreeString` at `0x18000731e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000731e`
- `OLEAUT32!__imp_VariantInit` at `0x180007115`
- `OLEAUT32!__imp_VariantInit` at `0x180007115`
- `OLEAUT32!__imp_VariantClear` at `0x1800072de`
- `OLEAUT32!__imp_VariantClear` at `0x1800072de`

## pseudocode

```c
// TaskScheduler COM sink toggles fixed task names opened under \Microsoft\Windows\DiskDiagnostic, not caller-controlled XML/action/working directory.
__int64 __fastcall DfdTask::ChangeDFDTaskStatus(DfdTask *this, const unsigned __int16 *a2, unsigned __int8 a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rsi
  unsigned int v8; // ebx
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  const wchar_t *v12; // r9
  __int64 v13; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v17; // [rsp+90h] [rbp+30h] BYREF
  __int16 v18; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+48h] BYREF

  v17 = 0;
  v19 = 0;
  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( *(_QWORD *)this && *((_QWORD *)this + 2) )
  {
    v6 = SysAllocString(a2);
    v7 = v6;
    if ( !v6 )
    {
      v8 = -2147024882;
      goto LABEL_30;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 **))(**((_QWORD **)this + 2) + 104LL))(
           *((_QWORD *)this + 2),
           v6,
           &v17);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v17 + 80))(v17, &v18);
      v8 = v9;
      if ( v9 >= 0 )
      {
        if ( (a3 ^ 1) - 1 != v18 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64 *))(*v17 + 88))(v17);
          v8 = v9;
          if ( v9 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = L"enabled";
              if ( !a3 )
                v12 = L"disabled";
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4f3495666d7e372198f3636e22490d50_Traceguids, v12);
            }
            if ( !v18 )
            {
              v13 = *v17;
              v16 = pvarg;
              v9 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v13 + 96))(v17, &v16, &v19);
              v8 = v9;
              if ( v9 < 0 )
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v11 = 19;
                  goto LABEL_9;
                }
              }
            }
          }
          else
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 17;
              goto LABEL_9;
            }
          }
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 16;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 15;
LABEL_9:
        WPP_SF_d(v10[2], v11, WPP_4f3495666d7e372198f3636e22490d50_Traceguids, (unsigned int)v9);
      }
    }
  }
  else
  {
    v7 = 0;
    v8 = -2147467259;
  }
LABEL_30:
  VariantClear(&pvarg);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    v17 = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  return v8;
}

```

## disassembly

```asm
0x1800070d8  mov     [rsp-28h+arg_8], rbx; TaskScheduler COM sink toggles fixed task names opened under \Microsoft\Windows\DiskDiagnostic, not caller-controlled XML/action/working directory.
0x1800070dd  push    rbp
0x1800070de  push    rsi
0x1800070df  push    rdi
0x1800070e0  push    r14
0x1800070e2  push    r15
0x1800070e4  mov     rbp, rsp
0x1800070e7  sub     rsp, 60h
0x1800070eb  xor     r15d, r15d
0x1800070ee  mov     rbx, rcx
0x1800070f1  xorps   xmm0, xmm0
0x1800070f4  mov     [rbp+arg_0], r15
0x1800070f8  xor     eax, eax
0x1800070fa  mov     [rbp+arg_18], r15
0x1800070fe  lea     rcx, [rbp+pvarg]; pvarg
0x180007102  mov     [rbp+arg_10], r15w
0x180007107  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000710b  mov     qword ptr [rbp+pvarg+10h], rax
0x18000710f  mov     r14b, r8b
0x180007112  mov     rdi, rdx
0x180007115  call    cs:__imp_VariantInit
0x18000711b  cmp     [rbx], r15
0x18000711e  jz      loc_1800072D2
0x180007124  cmp     [rbx+10h], r15
0x180007128  jz      loc_1800072D2
0x18000712e  mov     rcx, rdi; psz
0x180007131  call    cs:__imp_SysAllocString
0x180007137  mov     rsi, rax
0x18000713a  test    rax, rax
0x18000713d  jnz     short loc_180007149
0x18000713f  mov     ebx, 8007000Eh
0x180007144  jmp     loc_1800072DA
0x180007149  mov     rcx, [rbx+10h]
0x18000714d  lea     r8, [rbp+arg_0]
0x180007151  mov     rdx, rsi
0x180007154  mov     rax, [rcx]
0x180007157  mov     rax, [rax+68h]
0x18000715b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007160  mov     ebx, eax
0x180007162  test    eax, eax
0x180007164  jns     short loc_1800071A4
0x180007166  mov     rcx, cs:WPP_GLOBAL_Control
0x18000716d  lea     rdi, WPP_GLOBAL_Control
0x180007174  cmp     rcx, rdi
0x180007177  jz      loc_1800072DA
0x18000717d  test    byte ptr [rcx+1Ch], 1
0x180007181  jz      loc_1800072DA
0x180007187  mov     edx, 0Fh
0x18000718c  mov     rcx, [rcx+10h]
0x180007190  lea     r8, WPP_4f3495666d7e372198f3636e22490d50_Traceguids
0x180007197  mov     r9d, eax
0x18000719a  call    WPP_SF_d
0x18000719f  jmp     loc_1800072DA
0x1800071a4  mov     rcx, [rbp+arg_0]
0x1800071a8  lea     rdx, [rbp+arg_10]
0x1800071ac  mov     rax, [rcx]
0x1800071af  mov     rax, [rax+50h]
0x1800071b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b8  mov     ebx, eax
0x1800071ba  test    eax, eax
0x1800071bc  jns     short loc_1800071E6
0x1800071be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071c5  lea     rdi, WPP_GLOBAL_Control
0x1800071cc  cmp     rcx, rdi
0x1800071cf  jz      loc_1800072DA
0x1800071d5  test    byte ptr [rcx+1Ch], 1
0x1800071d9  jz      loc_1800072DA
0x1800071df  mov     edx, 10h
0x1800071e4  jmp     short loc_18000718C
0x1800071e6  mov     al, r14b
0x1800071e9  xor     al, 1
0x1800071eb  movzx   edx, al
0x1800071ee  dec     dx
0x1800071f1  cmp     dx, [rbp+arg_10]
0x1800071f5  jz      loc_1800072DA
0x1800071fb  mov     rcx, [rbp+arg_0]
0x1800071ff  mov     rax, [rcx]
0x180007202  mov     rax, [rax+58h]
0x180007206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720b  mov     ebx, eax
0x18000720d  test    eax, eax
0x18000720f  jns     short loc_18000723C
0x180007211  mov     rcx, cs:WPP_GLOBAL_Control
0x180007218  lea     rdi, WPP_GLOBAL_Control
0x18000721f  cmp     rcx, rdi
0x180007222  jz      loc_1800072DA
0x180007228  test    byte ptr [rcx+1Ch], 1
0x18000722c  jz      loc_1800072DA
0x180007232  mov     edx, 11h
0x180007237  jmp     loc_18000718C
0x18000723c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007243  lea     rdi, WPP_GLOBAL_Control
0x18000724a  cmp     rcx, rdi
0x18000724d  jz      short loc_18000727F
0x18000724f  test    byte ptr [rcx+1Ch], 1
0x180007253  jz      short loc_18000727F
0x180007255  mov     rcx, [rcx+10h]
0x180007259  lea     rax, aDisabled; "disabled"
0x180007260  test    r14b, r14b
0x180007263  lea     r9, aEnabled; "enabled"
0x18000726a  mov     edx, 12h
0x18000726f  lea     r8, WPP_4f3495666d7e372198f3636e22490d50_Traceguids
0x180007276  cmovz   r9, rax
0x18000727a  call    WPP_SF_S
0x18000727f  cmp     [rbp+arg_10], r15w
0x180007284  jnz     short loc_1800072DA
0x180007286  mov     rcx, [rbp+arg_0]
0x18000728a  lea     r8, [rbp+arg_18]
0x18000728e  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180007292  lea     rdx, [rbp+var_20]
0x180007296  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000729b  mov     rax, [rcx]
0x18000729e  movaps  [rbp+var_20], xmm0
0x1800072a2  movsd   [rbp+var_10], xmm1
0x1800072a7  mov     rax, [rax+60h]
0x1800072ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b0  mov     ebx, eax
0x1800072b2  test    eax, eax
0x1800072b4  jns     short loc_1800072DA
0x1800072b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072bd  cmp     rcx, rdi
0x1800072c0  jz      short loc_1800072DA
0x1800072c2  test    byte ptr [rcx+1Ch], 1
0x1800072c6  jz      short loc_1800072DA
0x1800072c8  mov     edx, 13h
0x1800072cd  jmp     loc_18000718C
0x1800072d2  mov     rsi, r15
0x1800072d5  mov     ebx, 80004005h
0x1800072da  lea     rcx, [rbp+pvarg]; pvarg
0x1800072de  call    cs:__imp_VariantClear
0x1800072e4  mov     rcx, [rbp+arg_18]
0x1800072e8  test    rcx, rcx
0x1800072eb  jz      short loc_1800072FD
0x1800072ed  mov     rax, [rcx]
0x1800072f0  mov     rax, [rax+10h]
0x1800072f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f9  mov     [rbp+arg_18], r15
0x1800072fd  mov     rcx, [rbp+arg_0]
0x180007301  test    rcx, rcx
0x180007304  jz      short loc_180007316
0x180007306  mov     rax, [rcx]
0x180007309  mov     rax, [rax+10h]
0x18000730d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007312  mov     [rbp+arg_0], r15
0x180007316  test    rsi, rsi
0x180007319  jz      short loc_180007324
0x18000731b  mov     rcx, rsi; bstrString
0x18000731e  call    cs:__imp_SysFreeString
0x180007324  mov     eax, ebx
0x180007326  mov     rbx, [rsp+60h+arg_8]
0x18000732e  add     rsp, 60h
0x180007332  pop     r15
0x180007334  pop     r14
0x180007336  pop     rdi
0x180007337  pop     rsi
0x180007338  pop     rbp
0x180007339  retn
```
