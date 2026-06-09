# WdipWriteParameterToMessageBuffer(__WDIP_PARAMETER *,_DPS_MESSAGE *,ulong,uchar * *)

- ea: `0x180018370`
- end: `0x180018678`
- name: `?WdipWriteParameterToMessageBuffer@@YAJPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@KPEAPEAE@Z`
- size: `776`
- prototype: `__int64 __fastcall(struct __WDIP_PARAMETER *, struct _DPS_MESSAGE *, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800099bc`

## callees

- `0x180009090`
- `0x180010fbc`
- `0x180018370`
- `0x180018b49`

## string_xrefs

- `0x1800183b8`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180018658`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800183b1`: `WdipWriteParameterToMessageBuffer`
- `0x180018651`: `WdipWriteParameterToMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipWriteParameterToMessageBuffer(
        struct __WDIP_PARAMETER *a1,
        struct _DPS_MESSAGE *a2,
        unsigned int a3,
        unsigned __int8 **a4)
{
  unsigned __int64 v4; // rsi
  int v8; // r8d
  unsigned int v9; // ebx
  int Args; // eax
  unsigned __int64 v11; // r11
  int v12; // r9d
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  char *v15; // r8
  __int128 v16; // xmm0
  struct _DPS_MESSAGE *v17; // rdx
  int v18; // r8d
  struct _DPS_MESSAGE *v19; // rdx
  struct _DPS_MESSAGE *v20; // rdx
  struct _DPS_MESSAGE *v21; // rdx
  int v22; // eax
  bool v23; // zf
  unsigned __int8 *v24; // r11
  unsigned __int64 v25; // rsi
  unsigned int v26; // ecx
  __int64 v27; // r15
  unsigned __int8 *v28; // rsi
  unsigned __int8 *v29; // rsi
  size_t v30; // r8
  unsigned __int64 v32; // [rsp+70h] [rbp+8h] BYREF

  v4 = a3;
  v32 = 0;
  if ( !a1 )
  {
    v8 = 471;
LABEL_3:
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToMessageBuffer",
      v8,
      (int)L"Error = %d",
      87);
    return v9;
  }
  if ( !a2 )
  {
    v8 = 472;
    goto LABEL_3;
  }
  if ( !*a4 )
  {
    v8 = 473;
    goto LABEL_3;
  }
  Args = StringCchLengthW(*((const unsigned __int16 **)a1 + 6), (unsigned __int64)a2, &v32);
  v9 = Args;
  if ( Args >= 0 )
  {
    v12 = v32;
    if ( v32 <= 0xFFFFFFFF )
    {
      if ( v11 < (unsigned __int64)a2
        || (v13 = v4, v14 = v11 - (_QWORD)a2, v11 - (unsigned __int64)a2 > v4)
        || (v15 = (char *)a2 + v4 - v11, (unsigned __int64)v15 < 0x10) )
      {
        v18 = 490;
      }
      else
      {
        v16 = *(_OWORD *)a1;
        v17 = (struct _DPS_MESSAGE *)(v11 + 16);
        *a4 = (unsigned __int8 *)(v11 + 16);
        *(_OWORD *)v11 = v16;
        if ( v11 == -16 || v17 < a2 || v14 + 16 > v4 || (unsigned __int64)(v15 - 16) < 0x10 )
        {
          v18 = 501;
        }
        else
        {
          *(_OWORD *)v17 = *((_OWORD *)a1 + 1);
          v19 = (struct _DPS_MESSAGE *)(v11 + 32);
          *a4 = (unsigned __int8 *)(v11 + 32);
          if ( v11 == -32 || v19 < a2 || v14 + 32 > v4 || (unsigned __int64)(v15 - 32) < 4 )
          {
            v18 = 512;
          }
          else
          {
            *(_DWORD *)v19 = *((_DWORD *)a1 + 8);
            v20 = (struct _DPS_MESSAGE *)(v11 + 36);
            *a4 = (unsigned __int8 *)(v11 + 36);
            if ( v11 == -36 || v20 < a2 || v14 + 36 > v4 || (unsigned __int64)(v15 - 36) < 4 )
            {
              v18 = 523;
            }
            else
            {
              *(_DWORD *)v20 = *((_DWORD *)a1 + 9);
              v21 = (struct _DPS_MESSAGE *)(v11 + 40);
              *a4 = (unsigned __int8 *)(v11 + 40);
              if ( v11 == -40 || v21 < a2 || v14 + 40 > v4 || (unsigned __int64)(v15 - 40) < 4 )
              {
                v18 = 534;
              }
              else
              {
                v22 = *((_DWORD *)a1 + 11);
                v23 = v11 == -44;
                v24 = (unsigned __int8 *)(v11 + 44);
                *a4 = v24;
                *(_DWORD *)v21 = v22;
                if ( v23
                  || v24 < (unsigned __int8 *)a2
                  || v24 - (unsigned __int8 *)a2 > v4
                  || (unsigned __int64)a2 + v4 - (_QWORD)v24 < 4 )
                {
                  v18 = 545;
                }
                else
                {
                  v25 = (unsigned __int64)(v24 + 4);
                  *a4 = v24 + 4;
                  v26 = 2 * v12 + 2;
                  *(_DWORD *)v24 = v26;
                  if ( v24 == (unsigned __int8 *)-4LL
                    || v25 < (unsigned __int64)a2
                    || v25 - (unsigned __int64)a2 > v13
                    || (v27 = v26, v26 > (unsigned __int64)a2 + v13 - v25) )
                  {
                    v18 = 556;
                  }
                  else
                  {
                    memcpy_0(v24 + 4, *((const void **)a1 + 6), v26);
                    v23 = v27 + v25 == 0;
                    v28 = (unsigned __int8 *)(v27 + v25);
                    *a4 = v28;
                    if ( v23
                      || v28 < (unsigned __int8 *)a2
                      || v28 - (unsigned __int8 *)a2 > v13
                      || (unsigned __int64)a2 + v13 - (_QWORD)v28 < 4 )
                    {
                      v18 = 567;
                    }
                    else
                    {
                      *(_DWORD *)v28 = *((_DWORD *)a1 + 10);
                      v23 = v28 + 4 == 0;
                      v29 = v28 + 4;
                      *a4 = v29;
                      if ( !v23 && v29 >= (unsigned __int8 *)a2 && v29 - (unsigned __int8 *)a2 <= v13 )
                      {
                        v30 = *((unsigned int *)a1 + 10);
                        if ( v30 <= (unsigned __int64)a2 + v13 - (_QWORD)v29 )
                        {
                          v9 = 0;
                          memcpy_0(v29, *((const void **)a1 + 7), v30);
                          *a4 = &v29[*((unsigned int *)a1 + 10)];
                          return v9;
                        }
                      }
                      v18 = 578;
                    }
                  }
                }
              }
            }
          }
        }
      }
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
        (int)L"WdipWriteParameterToMessageBuffer",
        v18,
        (int)L"Error = %d",
        111);
      return (unsigned int)-2147024362;
    }
    v9 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToMessageBuffer",
      482,
      (int)L"Error = %d",
      22);
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToMessageBuffer",
      479,
      (int)L"Error = %d",
      Args);
  }
  return v9;
}

```

## disassembly

```asm
0x180018370  push    rbx
0x180018372  push    rbp
0x180018373  push    rsi
0x180018374  push    rdi
0x180018375  push    r14
0x180018377  push    r15
0x180018379  sub     rsp, 38h
0x18001837d  mov     esi, r8d
0x180018380  mov     r14, r9
0x180018383  mov     [rsp+68h+arg_0], 0
0x18001838c  mov     rdi, rdx
0x18001838f  mov     rbp, rcx
0x180018392  test    rcx, rcx
0x180018395  jnz     short loc_1800183C9
0x180018397  mov     r8d, 1D7h; int
0x18001839d  mov     ebx, 80070057h
0x1800183a2  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x1800183aa  lea     r9, aErrorD; "Error = %d"
0x1800183b1  lea     rdx, aWdipwriteparam_0; "WdipWriteParameterToMessageBuffer"
0x1800183b8  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800183bf  call    WdipTraceError
0x1800183c4  jmp     loc_180018669
0x1800183c9  test    rdi, rdi
0x1800183cc  jnz     short loc_1800183D6
0x1800183ce  mov     r8d, 1D8h
0x1800183d4  jmp     short loc_18001839D
0x1800183d6  mov     r11, [r9]
0x1800183d9  test    r11, r11
0x1800183dc  jnz     short loc_1800183E6
0x1800183de  mov     r8d, 1D9h
0x1800183e4  jmp     short loc_18001839D
0x1800183e6  mov     rcx, [rcx+30h]; unsigned __int16 *
0x1800183ea  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x1800183ef  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800183f4  mov     ebx, eax
0x1800183f6  test    eax, eax
0x1800183f8  jns     short loc_180018409
0x1800183fa  movzx   ecx, ax
0x1800183fd  mov     r8d, 1DFh
0x180018403  mov     dword ptr [rsp+68h+Args], ecx
0x180018407  jmp     short loc_1800183AA
0x180018409  mov     r9, [rsp+68h+arg_0]
0x18001840e  mov     eax, 0FFFFFFFFh
0x180018413  cmp     r9, rax
0x180018416  jbe     short loc_180018430
0x180018418  mov     ebx, 80070216h
0x18001841d  mov     dword ptr [rsp+68h+Args], 216h
0x180018425  mov     r8d, 1E2h
0x18001842b  jmp     loc_1800183AA
0x180018430  cmp     r11, rdi
0x180018433  jb      loc_18001863C
0x180018439  mov     rcx, r11
0x18001843c  mov     rbx, rsi
0x18001843f  sub     rcx, rdi
0x180018442  cmp     rcx, rsi
0x180018445  ja      loc_18001863C
0x18001844b  mov     r8, rbx
0x18001844e  sub     r8, r11
0x180018451  add     r8, rdi
0x180018454  cmp     r8, 10h
0x180018458  jb      loc_18001863C
0x18001845e  movups  xmm0, xmmword ptr [rbp+0]
0x180018462  lea     rdx, [r11+10h]
0x180018466  mov     [r14], rdx
0x180018469  movdqu  xmmword ptr [r11], xmm0
0x18001846e  test    rdx, rdx
0x180018471  jz      short loc_180018481
0x180018473  cmp     rdx, rdi
0x180018476  jb      short loc_180018481
0x180018478  lea     rax, [rcx+10h]
0x18001847c  cmp     rax, rbx
0x18001847f  jbe     short loc_18001848C
0x180018481  mov     r8d, 1F5h
0x180018487  jmp     loc_180018642
0x18001848c  lea     rax, [r8-10h]
0x180018490  cmp     rax, 10h
0x180018494  jb      short loc_180018481
0x180018496  movups  xmm0, xmmword ptr [rbp+10h]
0x18001849a  movdqu  xmmword ptr [rdx], xmm0
0x18001849e  lea     rdx, [r11+20h]
0x1800184a2  mov     [r14], rdx
0x1800184a5  test    rdx, rdx
0x1800184a8  jz      short loc_1800184B8
0x1800184aa  cmp     rdx, rdi
0x1800184ad  jb      short loc_1800184B8
0x1800184af  lea     rax, [rcx+20h]
0x1800184b3  cmp     rax, rbx
0x1800184b6  jbe     short loc_1800184C3
0x1800184b8  mov     r8d, 200h
0x1800184be  jmp     loc_180018642
0x1800184c3  lea     rax, [r8-20h]
0x1800184c7  cmp     rax, 4
0x1800184cb  jb      short loc_1800184B8
0x1800184cd  mov     eax, [rbp+20h]
0x1800184d0  mov     [rdx], eax
0x1800184d2  lea     rdx, [r11+24h]
0x1800184d6  mov     [r14], rdx
0x1800184d9  test    rdx, rdx
0x1800184dc  jz      short loc_1800184EC
0x1800184de  cmp     rdx, rdi
0x1800184e1  jb      short loc_1800184EC
0x1800184e3  lea     rax, [rcx+24h]
0x1800184e7  cmp     rax, rbx
0x1800184ea  jbe     short loc_1800184F7
0x1800184ec  mov     r8d, 20Bh
0x1800184f2  jmp     loc_180018642
0x1800184f7  lea     rax, [r8-24h]
0x1800184fb  cmp     rax, 4
0x1800184ff  jb      short loc_1800184EC
0x180018501  mov     eax, [rbp+24h]
0x180018504  mov     [rdx], eax
0x180018506  lea     rdx, [r11+28h]
0x18001850a  mov     [r14], rdx
0x18001850d  test    rdx, rdx
0x180018510  jz      short loc_180018520
0x180018512  cmp     rdx, rdi
0x180018515  jb      short loc_180018520
0x180018517  lea     rax, [rcx+28h]
0x18001851b  cmp     rax, rbx
0x18001851e  jbe     short loc_18001852B
0x180018520  mov     r8d, 216h
0x180018526  jmp     loc_180018642
0x18001852b  lea     rax, [r8-28h]
0x18001852f  cmp     rax, 4
0x180018533  jb      short loc_180018520
0x180018535  mov     eax, [rbp+2Ch]
0x180018538  add     r11, 2Ch ; ','
0x18001853c  mov     [r14], r11
0x18001853f  mov     [rdx], eax
0x180018541  jz      short loc_180018553
0x180018543  cmp     r11, rdi
0x180018546  jb      short loc_180018553
0x180018548  mov     rax, r11
0x18001854b  sub     rax, rdi
0x18001854e  cmp     rax, rbx
0x180018551  jbe     short loc_18001855E
0x180018553  mov     r8d, 221h
0x180018559  jmp     loc_180018642
0x18001855e  mov     rax, rbx
0x180018561  sub     rax, r11
0x180018564  add     rax, rdi
0x180018567  cmp     rax, 4
0x18001856b  jb      short loc_180018553
0x18001856d  lea     rsi, [r11+4]
0x180018571  mov     [r14], rsi
0x180018574  lea     ecx, ds:2[r9*2]
0x18001857c  mov     [r11], ecx
0x18001857f  test    rsi, rsi
0x180018582  jz      short loc_180018594
0x180018584  cmp     rsi, rdi
0x180018587  jb      short loc_180018594
0x180018589  mov     rax, rsi
0x18001858c  sub     rax, rdi
0x18001858f  cmp     rax, rbx
0x180018592  jbe     short loc_18001859F
0x180018594  mov     r8d, 22Ch
0x18001859a  jmp     loc_180018642
0x18001859f  mov     rax, rbx
0x1800185a2  mov     r15d, ecx
0x1800185a5  sub     rax, rsi
0x1800185a8  add     rax, rdi
0x1800185ab  cmp     r15, rax
0x1800185ae  ja      short loc_180018594
0x1800185b0  mov     rdx, [rbp+30h]; Src
0x1800185b4  mov     r8d, r15d; Size
0x1800185b7  mov     rcx, rsi; void *
0x1800185ba  call    memcpy_0
0x1800185bf  add     rsi, r15
0x1800185c2  mov     [r14], rsi
0x1800185c5  jz      short loc_1800185D7
0x1800185c7  cmp     rsi, rdi
0x1800185ca  jb      short loc_1800185D7
0x1800185cc  mov     rax, rsi
0x1800185cf  sub     rax, rdi
0x1800185d2  cmp     rax, rbx
0x1800185d5  jbe     short loc_1800185DF
0x1800185d7  mov     r8d, 237h
0x1800185dd  jmp     short loc_180018642
0x1800185df  mov     rax, rbx
0x1800185e2  sub     rax, rsi
0x1800185e5  add     rax, rdi
0x1800185e8  cmp     rax, 4
0x1800185ec  jb      short loc_1800185D7
0x1800185ee  mov     eax, [rbp+28h]
0x1800185f1  mov     [rsi], eax
0x1800185f3  add     rsi, 4
0x1800185f7  mov     [r14], rsi
0x1800185fa  jz      short loc_18001860C
0x1800185fc  cmp     rsi, rdi
0x1800185ff  jb      short loc_18001860C
0x180018601  mov     rax, rsi
0x180018604  sub     rax, rdi
0x180018607  cmp     rax, rbx
0x18001860a  jbe     short loc_180018614
0x18001860c  mov     r8d, 242h
0x180018612  jmp     short loc_180018642
0x180018614  mov     r8d, [rbp+28h]; Size
0x180018618  sub     rbx, rsi
0x18001861b  add     rbx, rdi
0x18001861e  cmp     r8, rbx
0x180018621  ja      short loc_18001860C
0x180018623  mov     rdx, [rbp+38h]; Src
0x180018627  mov     rcx, rsi; void *
0x18001862a  xor     ebx, ebx
0x18001862c  call    memcpy_0
0x180018631  mov     eax, [rbp+28h]
0x180018634  add     rax, rsi
0x180018637  mov     [r14], rax
0x18001863a  jmp     short loc_180018669
0x18001863c  mov     r8d, 1EAh; int
0x180018642  lea     r9, aErrorD; "Error = %d"
0x180018649  mov     dword ptr [rsp+68h+Args], 6Fh ; 'o'; Args
0x180018651  lea     rdx, aWdipwriteparam_0; "WdipWriteParameterToMessageBuffer"
0x180018658  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001865f  call    WdipTraceError
0x180018664  mov     ebx, 80070216h
0x180018669  mov     eax, ebx
0x18001866b  add     rsp, 38h
0x18001866f  pop     r15
0x180018671  pop     r14
0x180018673  pop     rdi
0x180018674  pop     rsi
0x180018675  pop     rbp
0x180018676  pop     rbx
0x180018677  retn
```
