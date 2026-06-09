# TableQueryInterpreter::AcceptIf(int,tagCondition * const)

- ea: `0x1800085f0`
- end: `0x180008930`
- name: `?AcceptIf@TableQueryInterpreter@@UEAAJHQEAUtagCondition@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(TableQueryInterpreter *__hidden this, int, struct tagCondition *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800085f0`
- `0x180008938`
- `0x180021374`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800086d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008727`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008920`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800086d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008727`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008763`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000869d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000869d`

## string_xrefs

- `0x18000888a`: `com\complus\src\events\tier3\regdb\table.cpp`

## pseudocode

```c
__int64 __fastcall TableQueryInterpreter::AcceptIf(TableQueryInterpreter *this, int a2, struct tagCondition *const a3)
{
  __int64 *v3; // r12
  __int64 v4; // r14
  char v8; // di
  __int64 v9; // rax
  unsigned int *v10; // rsi
  HRESULT v11; // eax
  HRESULT v12; // ebx
  __int16 v13; // ax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  bool v16; // zf
  unsigned int v17; // eax
  __int64 result; // rax
  __int16 v19; // dx
  unsigned int v20; // ecx
  __int64 v21; // rbx
  __int64 v22; // r15
  __int64 v23; // rbp
  _QWORD *v24; // rax
  int v25; // r8d
  _QWORD *i; // rcx
  _QWORD *v27; // rdi
  _QWORD *v28; // rcx
  int v29; // eax
  _QWORD *v30; // rax
  LPCOLESTR v31; // rax
  int v32; // ecx
  int v33; // edx
  LPCOLESTR lpsz[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v35; // [rsp+30h] [rbp-58h]
  GUID pclsid; // [rsp+38h] [rbp-50h] BYREF

  v3 = (__int64 *)*((_QWORD *)this + 5);
  v4 = 0;
  v8 = 1;
  while ( (int)v4 < a2 )
  {
    v35 = 0;
    v9 = *v3;
    v10 = (unsigned int *)((char *)a3 + 40 * v4);
    *(_OWORD *)lpsz = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, LPCOLESTR *))(v9 + 24))(v3, *v10, lpsz);
    v12 = v11;
    if ( v11 == 1 )
    {
      v19 = *((_WORD *)v10 + 4);
      v20 = v10[8];
      if ( v20 == 1 )
      {
        v8 = v19 == 0;
        PropVariantClear((PROPVARIANT *)lpsz);
        goto LABEL_16;
      }
      if ( v20 == -2 )
      {
        v8 = v19 != 0;
        PropVariantClear((PROPVARIANT *)lpsz);
        goto LABEL_16;
      }
      v12 = -2147418113;
    }
    else if ( !v11 )
    {
      v13 = *((_WORD *)v10 + 4);
      v8 = 0;
      if ( v13 == 72 )
      {
        if ( LOWORD(lpsz[0]) == 8 )
        {
          pclsid = 0;
          v12 = CLSIDFromString(lpsz[1], &pclsid);
          if ( v12 >= 0 )
          {
            v14 = (_QWORD *)*((_QWORD *)v10 + 2);
            v15 = *(_QWORD *)&pclsid.Data1 - *v14;
            if ( *(_QWORD *)&pclsid.Data1 == *v14 )
              v15 = *(_QWORD *)pclsid.Data4 - v14[1];
            v16 = v15 == 0;
LABEL_10:
            v8 = v16;
          }
        }
      }
      else if ( v13 )
      {
        if ( v13 == 31 )
        {
          if ( LOWORD(lpsz[0]) == 8 )
          {
            v31 = lpsz[1];
            do
            {
              v32 = *(LPCOLESTR)((char *)v31 + *((_QWORD *)v10 + 2) - (unsigned __int64)lpsz[1]);
              v33 = *v31 - v32;
              if ( v33 )
                break;
              ++v31;
            }
            while ( v32 );
            v16 = v33 == 0;
            goto LABEL_10;
          }
        }
        else if ( v13 == 11 )
        {
          if ( LOWORD(lpsz[0]) == 11 )
          {
            v16 = LOWORD(lpsz[1]) == *((_WORD *)v10 + 8);
            goto LABEL_10;
          }
        }
        else
        {
          v12 = -2147316576;
        }
      }
      v17 = v10[8];
      if ( v17 != 1 )
      {
        if ( v17 != -2 )
        {
          PropVariantClear((PROPVARIANT *)lpsz);
          return 2147500037LL;
        }
        v8 ^= 1u;
      }
    }
    PropVariantClear((PROPVARIANT *)lpsz);
    if ( v12 < 0 )
      return (unsigned int)v12;
LABEL_16:
    if ( !v8 )
      return 1;
    v4 = (unsigned int)(v4 + 1);
  }
  v21 = *((_QWORD *)this + 2);
  v22 = *((_QWORD *)this + 5);
  v23 = *(_QWORD *)(v21 + 24);
  if ( !*(_QWORD *)(v21 + 40) )
  {
    v24 = CoTaskMemAlloc((unsigned int)(24 * *(_DWORD *)(v21 + 56)) + 8LL);
    if ( !v24 )
    {
LABEL_38:
      InternalError_HR(L"com\\complus\\src\\events\\tier3\\regdb\\table.cpp", 0x2D3u, 0x11u, -2147024882);
      ++*(_DWORD *)(v21 + 76);
      return 0;
    }
    *v24 = *(_QWORD *)(v21 + 48);
    *(_QWORD *)(v21 + 48) = v24;
    v25 = *(_DWORD *)(v21 + 56) - 1;
    for ( i = &v24[3 * v25 + 1]; v25 >= 0; --v25 )
    {
      *i = *(_QWORD *)(v21 + 40);
      *(_QWORD *)(v21 + 40) = i;
      i -= 3;
    }
  }
  v27 = *(_QWORD **)(v21 + 40);
  v28 = v27 + 2;
  *(_QWORD *)(v21 + 40) = *v27;
  v29 = 1;
  v27[1] = v23;
  *v27 = 0;
  ++*(_DWORD *)(v21 + 32);
  v27[2] = 0;
  do
  {
    *v28++ = 0;
    --v29;
  }
  while ( v29 );
  if ( !v27 )
    goto LABEL_38;
  RefCountedPointer<IEventObjectRow>::Clear(v27 + 2);
  v27[2] = v22;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  v30 = *(_QWORD **)(v21 + 24);
  if ( v30 )
    *v30 = v27;
  else
    *(_QWORD *)(v21 + 16) = v27;
  result = 0;
  *(_QWORD *)(v21 + 24) = v27;
  ++*(_DWORD *)(v21 + 76);
  return result;
}

```

## disassembly

```asm
0x1800085f0  mov     [rsp+arg_8], rbx
0x1800085f5  push    rbp
0x1800085f6  push    rsi
0x1800085f7  push    rdi
0x1800085f8  push    r12
0x1800085fa  push    r13
0x1800085fc  push    r14
0x1800085fe  push    r15
0x180008600  sub     rsp, 50h
0x180008604  mov     rax, cs:__security_cookie
0x18000860b  xor     rax, rsp
0x18000860e  mov     [rsp+88h+var_40], rax
0x180008613  mov     r12, [rcx+28h]
0x180008617  xor     r14d, r14d
0x18000861a  mov     r13, r8
0x18000861d  mov     r15d, edx
0x180008620  mov     rbp, rcx
0x180008623  mov     dil, 1
0x180008626  test    edx, edx
0x180008628  jle     loc_180008742
0x18000862e  xor     eax, eax
0x180008630  lea     rcx, [r14+r14*4]
0x180008634  lea     rsi, ds:0[rcx*8]
0x18000863c  mov     [rsp+88h+var_58], rax
0x180008641  mov     rax, [r12]
0x180008645  lea     r8, [rsp+88h+lpsz]
0x18000864a  xorps   xmm0, xmm0
0x18000864d  add     rsi, r13
0x180008650  mov     rcx, r12
0x180008653  movups  xmmword ptr [rsp+88h+lpsz], xmm0
0x180008658  mov     rax, [rax+18h]
0x18000865c  mov     edx, [rsi]
0x18000865e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008663  mov     ebx, eax
0x180008665  cmp     eax, 1
0x180008668  jz      loc_180008709
0x18000866e  test    eax, eax
0x180008670  jnz     short loc_1800086D3
0x180008672  movzx   eax, word ptr [rsi+8]
0x180008676  xor     dil, dil
0x180008679  cmp     ax, 48h ; 'H'
0x18000867d  jnz     loc_18000882E
0x180008683  cmp     word ptr [rsp+88h+lpsz], 8
0x180008689  jnz     short loc_1800086C7
0x18000868b  mov     rcx, [rsp+88h+lpsz+8]; lpsz
0x180008690  lea     rdx, [rsp+88h+pclsid]; pclsid
0x180008695  xorps   xmm0, xmm0
0x180008698  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x18000869d  call    cs:__imp_CLSIDFromString
0x1800086a3  mov     ebx, eax
0x1800086a5  test    eax, eax
0x1800086a7  js      short loc_1800086C7
0x1800086a9  mov     rcx, [rsi+10h]
0x1800086ad  mov     rax, qword ptr [rsp+88h+pclsid.Data1]
0x1800086b2  sub     rax, [rcx]
0x1800086b5  jnz     short loc_1800086C0
0x1800086b7  mov     rax, qword ptr [rsp+88h+pclsid.Data4]
0x1800086bc  sub     rax, [rcx+8]
0x1800086c0  test    rax, rax
0x1800086c3  setz    dil
0x1800086c7  mov     eax, [rsi+20h]
0x1800086ca  cmp     eax, 1
0x1800086cd  jnz     loc_18000890D
0x1800086d3  lea     rcx, [rsp+88h+lpsz]; pvar
0x1800086d8  call    cs:__imp_PropVariantClear
0x1800086de  test    ebx, ebx
0x1800086e0  jns     short loc_18000872D
0x1800086e2  mov     eax, ebx
0x1800086e4  mov     rcx, [rsp+88h+var_40]
0x1800086e9  xor     rcx, rsp; StackCookie
0x1800086ec  call    __security_check_cookie
0x1800086f1  mov     rbx, [rsp+88h+arg_8]
0x1800086f9  add     rsp, 50h
0x1800086fd  pop     r15
0x1800086ff  pop     r14
0x180008701  pop     r13
0x180008703  pop     r12
0x180008705  pop     rdi
0x180008706  pop     rsi
0x180008707  pop     rbp
0x180008708  retn
0x180008709  movzx   edx, word ptr [rsi+8]
0x18000870d  mov     ecx, [rsi+20h]
0x180008710  test    dx, dx
0x180008713  setz    al
0x180008716  cmp     ecx, 1
0x180008719  jnz     loc_1800088BD
0x18000871f  lea     rcx, [rsp+88h+lpsz]; pvar
0x180008724  movzx   edi, al
0x180008727  call    cs:__imp_PropVariantClear
0x18000872d  test    dil, dil
0x180008730  jz      loc_18000887B
0x180008736  inc     r14d
0x180008739  cmp     r14d, r15d
0x18000873c  jl      loc_18000862E
0x180008742  mov     rbx, [rbp+10h]
0x180008746  xor     esi, esi
0x180008748  mov     r15, [rbp+28h]
0x18000874c  mov     rbp, [rbx+18h]
0x180008750  cmp     [rbx+28h], rsi
0x180008754  jnz     short loc_1800087B5
0x180008756  mov     eax, [rbx+38h]
0x180008759  lea     ecx, [rax+rax*2]
0x18000875c  shl     ecx, 3
0x18000875f  add     rcx, 8; cb
0x180008763  call    cs:__imp_CoTaskMemAlloc
0x180008769  test    rax, rax
0x18000876c  jz      loc_180008885
0x180008772  mov     rcx, [rbx+30h]
0x180008776  mov     [rax], rcx
0x180008779  mov     [rbx+30h], rax
0x18000877d  mov     r8d, [rbx+38h]
0x180008781  sub     r8d, 1
0x180008785  movsxd  rcx, r8d
0x180008788  lea     rcx, [rcx+rcx*2]
0x18000878c  lea     rcx, [rcx+1]
0x180008790  lea     rcx, [rax+rcx*8]
0x180008794  js      short loc_1800087B5
0x180008796  nop     word ptr [rax+rax+00000000h]
0x1800087a0  mov     rax, [rbx+28h]
0x1800087a4  mov     [rcx], rax
0x1800087a7  mov     [rbx+28h], rcx
0x1800087ab  sub     rcx, 18h
0x1800087af  sub     r8d, 1
0x1800087b3  jns     short loc_1800087A0
0x1800087b5  mov     rdi, [rbx+28h]
0x1800087b9  mov     rax, [rdi]
0x1800087bc  lea     rcx, [rdi+10h]
0x1800087c0  mov     [rbx+28h], rax
0x1800087c4  mov     eax, 1
0x1800087c9  mov     [rdi+8], rbp
0x1800087cd  mov     [rdi], rsi
0x1800087d0  inc     dword ptr [rbx+20h]
0x1800087d3  xor     edx, edx
0x1800087d5  mov     [rdi+10h], rdx
0x1800087d9  mov     [rcx], rdx
0x1800087dc  lea     rcx, [rcx+8]
0x1800087e0  sub     eax, 1
0x1800087e3  jnz     short loc_1800087D9
0x1800087e5  test    rdi, rdi
0x1800087e8  jz      loc_180008885
0x1800087ee  lea     rcx, [rdi+10h]
0x1800087f2  call    ?Clear@?$RefCountedPointer@UIEventObjectRow@@@@AEAAXXZ; RefCountedPointer<IEventObjectRow>::Clear(void)
0x1800087f7  mov     [rdi+10h], r15
0x1800087fb  test    r15, r15
0x1800087fe  jz      short loc_18000880F
0x180008800  mov     rax, [r15]
0x180008803  mov     rcx, r15
0x180008806  mov     rax, [rax+8]
0x18000880a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880f  mov     rax, [rbx+18h]
0x180008813  test    rax, rax
0x180008816  jnz     loc_1800088AC
0x18000881c  mov     [rbx+10h], rdi
0x180008820  mov     eax, esi
0x180008822  mov     [rbx+18h], rdi
0x180008826  inc     dword ptr [rbx+4Ch]
0x180008829  jmp     loc_1800086E4
0x18000882e  test    ax, ax
0x180008831  jz      loc_1800086C7
0x180008837  cmp     ax, 1Fh
0x18000883b  jnz     loc_1800088E3
0x180008841  cmp     word ptr [rsp+88h+lpsz], 8
0x180008847  jnz     loc_1800086C7
0x18000884d  mov     rax, [rsp+88h+lpsz+8]
0x180008852  mov     r8, [rsi+10h]
0x180008856  sub     r8, rax
0x180008859  nop     dword ptr [rax+00000000h]
0x180008860  movzx   edx, word ptr [rax]
0x180008863  movzx   ecx, word ptr [rax+r8]
0x180008868  sub     edx, ecx
0x18000886a  jnz     short loc_180008874
0x18000886c  add     rax, 2
0x180008870  test    ecx, ecx
0x180008872  jnz     short loc_180008860
0x180008874  test    edx, edx
0x180008876  jmp     loc_1800086C3
0x18000887b  mov     eax, 1
0x180008880  jmp     loc_1800086E4
0x180008885  mov     edx, 2D3h; unsigned int
0x18000888a  lea     rcx, aComComplusSrcE_0; "com\\complus\\src\\events\\tier3\\regdb"...
0x180008891  mov     r8d, 11h; unsigned __int16
0x180008897  mov     r9d, 8007000Eh; int
0x18000889d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800088a2  inc     dword ptr [rbx+4Ch]
0x1800088a5  mov     eax, esi
0x1800088a7  jmp     loc_1800086E4
0x1800088ac  mov     [rax], rdi
0x1800088af  mov     eax, esi
0x1800088b1  mov     [rbx+18h], rdi
0x1800088b5  inc     dword ptr [rbx+4Ch]
0x1800088b8  jmp     loc_1800086E4
0x1800088bd  cmp     ecx, 0FFFFFFFEh
0x1800088c0  jnz     short loc_1800088D9
0x1800088c2  test    dx, dx
0x1800088c5  lea     rcx, [rsp+88h+lpsz]; pvar
0x1800088ca  setnz   dil
0x1800088ce  call    cs:__imp_PropVariantClear
0x1800088d4  jmp     loc_18000872D
0x1800088d9  mov     ebx, 8000FFFFh
0x1800088de  jmp     loc_1800086D3
0x1800088e3  cmp     ax, 0Bh
0x1800088e7  jz      short loc_1800088F3
0x1800088e9  mov     ebx, 80028CA0h
0x1800088ee  jmp     loc_1800086C7
0x1800088f3  cmp     word ptr [rsp+88h+lpsz], 0Bh
0x1800088f9  jnz     loc_1800086C7
0x1800088ff  movzx   eax, word ptr [rsi+10h]
0x180008903  cmp     word ptr [rsp+88h+lpsz+8], ax
0x180008908  jmp     loc_1800086C3
0x18000890d  cmp     eax, 0FFFFFFFEh
0x180008910  jnz     short loc_18000891B
0x180008912  xor     dil, 1
0x180008916  jmp     loc_1800086D3
0x18000891b  lea     rcx, [rsp+88h+lpsz]; pvar
0x180008920  call    cs:__imp_PropVariantClear
0x180008926  mov     eax, 80004005h
0x18000892b  jmp     loc_1800086E4
```
