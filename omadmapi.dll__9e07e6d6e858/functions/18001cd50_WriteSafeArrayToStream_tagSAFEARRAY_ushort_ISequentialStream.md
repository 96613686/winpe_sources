# WriteSafeArrayToStream(tagSAFEARRAY *,ushort,ISequentialStream *)

- ea: `0x18001cd50`
- end: `0x18001cf63`
- name: `?WriteSafeArrayToStream@@YAJPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16, struct ISequentialStream *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d5b0`

## callees

- `0x18001cd50`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001cdbd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001cdbd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001cd9b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001cd9b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001cf3c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001cf3c`

## pseudocode

```c
__int64 __fastcall WriteSafeArrayToStream(SAFEARRAY *psa, __int16 a2, struct ISequentialStream *a3)
{
  HRESULT UBound; // ebx
  struct ISequentialStreamVtbl *lpVtbl; // rax
  struct ISequentialStreamVtbl *v8; // rax
  int v9; // esi
  __int64 v10; // r15
  __int64 v11; // rcx
  _WORD *v12; // rax
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  int v16; // [rsp+80h] [rbp+40h] BYREF
  LONG plUbound; // [rsp+98h] [rbp+58h] BYREF

  ppvData = 0;
  plUbound = 0;
  v14 = 0;
  v16 = 0;
  if ( psa && a3 )
  {
    UBound = SafeArrayAccessData(psa, &ppvData);
    if ( UBound >= 0 )
    {
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( UBound >= 0 )
      {
        lpVtbl = a3->lpVtbl;
        ++plUbound;
        UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, LONG *, __int64, int *))lpVtbl->Write)(
                   a3,
                   &plUbound,
                   4,
                   &v16);
        if ( UBound >= 0 )
        {
          if ( v16 == 4 )
          {
            if ( a2 == 8 )
            {
              v9 = 0;
              if ( plUbound > 0 )
              {
                while ( 1 )
                {
                  v16 = 0;
                  v10 = *((_QWORD *)ppvData + v9);
                  if ( !v10 )
                    break;
                  v11 = 0x7FFFFFFF;
                  v12 = (_WORD *)*((_QWORD *)ppvData + v9);
                  do
                  {
                    if ( !*v12 )
                      break;
                    ++v12;
                    --v11;
                  }
                  while ( v11 );
                  UBound = v11 == 0 ? 0x80070057 : 0;
                  if ( !v11 )
                  {
                    v14 = 0;
                    goto LABEL_28;
                  }
                  v14 = 2 * (0x7FFFFFFF - v11);
                  UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, __int64 *, __int64, int *))a3->lpVtbl->Write)(
                             a3,
                             &v14,
                             8,
                             &v16);
                  if ( UBound < 0 )
                    goto LABEL_28;
                  if ( v16 != 8 )
                    goto LABEL_13;
                  UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, __int64, _QWORD, int *))a3->lpVtbl->Write)(
                             a3,
                             v10,
                             (unsigned int)v14,
                             &v16);
                  if ( UBound < 0 )
                    goto LABEL_28;
                  if ( v16 != v14 )
                    goto LABEL_13;
                  if ( ++v9 >= plUbound )
                    goto LABEL_28;
                }
                UBound = -2147024809;
              }
            }
            else if ( a2 == 17 )
            {
              v8 = a3->lpVtbl;
              v14 = plUbound;
              UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, void *, _QWORD, int *))v8->Write)(
                         a3,
                         ppvData,
                         plUbound,
                         &v16);
              if ( UBound >= 0 && v16 != v14 )
LABEL_13:
                UBound = -2147418113;
            }
          }
          else
          {
            UBound = -2147467259;
          }
        }
      }
    }
LABEL_28:
    if ( ppvData )
      SafeArrayUnaccessData(psa);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x18001cd50  mov     [rsp-38h+arg_8], rbx
0x18001cd55  push    rbp
0x18001cd56  push    rsi
0x18001cd57  push    rdi
0x18001cd58  push    r12
0x18001cd5a  push    r13
0x18001cd5c  push    r14
0x18001cd5e  push    r15
0x18001cd60  mov     rbp, rsp
0x18001cd63  sub     rsp, 40h
0x18001cd67  xor     r12d, r12d
0x18001cd6a  mov     rdi, r8
0x18001cd6d  mov     [rbp+ppvData], r12
0x18001cd71  movzx   esi, dx
0x18001cd74  mov     [rbp+plUbound], r12d
0x18001cd78  mov     r14, rcx
0x18001cd7b  mov     [rbp+var_10], r12
0x18001cd7f  mov     [rbp+arg_0], r12d
0x18001cd83  test    rcx, rcx
0x18001cd86  jnz     short loc_18001CD92
0x18001cd88  mov     ebx, 80004003h
0x18001cd8d  jmp     loc_18001CF48
0x18001cd92  test    rdi, rdi
0x18001cd95  jz      short loc_18001CD88
0x18001cd97  lea     rdx, [rbp+ppvData]; ppvData
0x18001cd9b  call    cs:__imp_SafeArrayAccessData
0x18001cda2  nop     dword ptr [rax+rax+00h]
0x18001cda7  mov     ebx, eax
0x18001cda9  test    eax, eax
0x18001cdab  js      loc_18001CF33
0x18001cdb1  lea     r8, [rbp+plUbound]; plUbound
0x18001cdb5  mov     edx, 1; nDim
0x18001cdba  mov     rcx, r14; psa
0x18001cdbd  call    cs:__imp_SafeArrayGetUBound
0x18001cdc4  nop     dword ptr [rax+rax+00h]
0x18001cdc9  mov     ebx, eax
0x18001cdcb  test    eax, eax
0x18001cdcd  js      loc_18001CF33
0x18001cdd3  mov     rax, [rdi]
0x18001cdd6  lea     r9, [rbp+arg_0]
0x18001cdda  inc     [rbp+plUbound]
0x18001cddd  lea     rdx, [rbp+plUbound]
0x18001cde1  mov     r8d, 4
0x18001cde7  mov     rcx, rdi
0x18001cdea  mov     rax, [rax+20h]
0x18001cdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdf3  mov     ebx, eax
0x18001cdf5  test    eax, eax
0x18001cdf7  js      loc_18001CF33
0x18001cdfd  cmp     [rbp+arg_0], 4
0x18001ce01  jz      short loc_18001CE0D
0x18001ce03  mov     ebx, 80004005h
0x18001ce08  jmp     loc_18001CF33
0x18001ce0d  mov     r13d, 8
0x18001ce13  cmp     si, r13w
0x18001ce17  jz      short loc_18001CE63
0x18001ce19  cmp     si, 11h
0x18001ce1d  jnz     loc_18001CF33
0x18001ce23  mov     rax, [rdi]
0x18001ce26  lea     r9, [rbp+arg_0]
0x18001ce2a  movsxd  r8, [rbp+plUbound]
0x18001ce2e  mov     rcx, rdi
0x18001ce31  mov     rdx, [rbp+ppvData]
0x18001ce35  mov     [rbp+var_10], r8
0x18001ce39  mov     rax, [rax+20h]
0x18001ce3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce42  mov     ebx, eax
0x18001ce44  test    eax, eax
0x18001ce46  js      loc_18001CF33
0x18001ce4c  mov     eax, [rbp+arg_0]
0x18001ce4f  cmp     rax, [rbp+var_10]
0x18001ce53  jz      loc_18001CF33
0x18001ce59  mov     ebx, 8000FFFFh
0x18001ce5e  jmp     loc_18001CF33
0x18001ce63  mov     esi, r12d
0x18001ce66  cmp     [rbp+plUbound], r12d
0x18001ce6a  jle     loc_18001CF33
0x18001ce70  mov     rax, [rbp+ppvData]
0x18001ce74  movsxd  rcx, esi
0x18001ce77  mov     [rbp+arg_0], r12d
0x18001ce7b  mov     r15, [rax+rcx*8]
0x18001ce7f  test    r15, r15
0x18001ce82  jz      loc_18001CF2E
0x18001ce88  mov     ecx, 7FFFFFFFh
0x18001ce8d  mov     rax, r15
0x18001ce90  cmp     [rax], r12w
0x18001ce94  jz      short loc_18001CEA0
0x18001ce96  add     rax, 2
0x18001ce9a  sub     rcx, 1
0x18001ce9e  jnz     short loc_18001CE90
0x18001cea0  mov     rax, rcx
0x18001cea3  neg     rax
0x18001cea6  sbb     ebx, ebx
0x18001cea8  not     ebx
0x18001ceaa  and     ebx, 80070057h
0x18001ceb0  test    rcx, rcx
0x18001ceb3  jz      short loc_18001CF28
0x18001ceb5  mov     eax, 7FFFFFFFh
0x18001ceba  lea     r9, [rbp+arg_0]
0x18001cebe  sub     rax, rcx
0x18001cec1  lea     rdx, [rbp+var_10]
0x18001cec5  add     rax, rax
0x18001cec8  mov     r8d, r13d
0x18001cecb  mov     [rbp+var_10], rax
0x18001cecf  mov     rcx, rdi
0x18001ced2  mov     rax, [rdi]
0x18001ced5  mov     rax, [rax+20h]
0x18001ced9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cede  mov     ebx, eax
0x18001cee0  test    eax, eax
0x18001cee2  js      short loc_18001CF33
0x18001cee4  cmp     [rbp+arg_0], r13d
0x18001cee8  jnz     loc_18001CE59
0x18001ceee  mov     rax, [rdi]
0x18001cef1  lea     r9, [rbp+arg_0]
0x18001cef5  mov     r8d, dword ptr [rbp+var_10]
0x18001cef9  mov     rdx, r15
0x18001cefc  mov     rcx, rdi
0x18001ceff  mov     rax, [rax+20h]
0x18001cf03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf08  mov     ebx, eax
0x18001cf0a  test    eax, eax
0x18001cf0c  js      short loc_18001CF33
0x18001cf0e  mov     eax, [rbp+arg_0]
0x18001cf11  cmp     rax, [rbp+var_10]
0x18001cf15  jnz     loc_18001CE59
0x18001cf1b  inc     esi
0x18001cf1d  cmp     esi, [rbp+plUbound]
0x18001cf20  jl      loc_18001CE70
0x18001cf26  jmp     short loc_18001CF33
0x18001cf28  mov     [rbp+var_10], r12
0x18001cf2c  jmp     short loc_18001CF33
0x18001cf2e  mov     ebx, 80070057h
0x18001cf33  cmp     [rbp+ppvData], r12
0x18001cf37  jz      short loc_18001CF48
0x18001cf39  mov     rcx, r14; psa
0x18001cf3c  call    cs:__imp_SafeArrayUnaccessData
0x18001cf43  nop     dword ptr [rax+rax+00h]
0x18001cf48  mov     eax, ebx
0x18001cf4a  mov     rbx, [rsp+40h+arg_8]
0x18001cf52  add     rsp, 40h
0x18001cf56  pop     r15
0x18001cf58  pop     r14
0x18001cf5a  pop     r13
0x18001cf5c  pop     r12
0x18001cf5e  pop     rdi
0x18001cf5f  pop     rsi
0x18001cf60  pop     rbp
0x18001cf61  retn
```
