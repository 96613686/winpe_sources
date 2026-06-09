# CSTATPROPBAGArray::NextAt(ulong,tagSTATPROPBAG *,ulong *)

- ea: `0x1800557bc`
- end: `0x180055918`
- name: `?NextAt@CSTATPROPBAGArray@@QEAAJKPEAUtagSTATPROPBAG@@PEAK@Z`
- size: `348`
- prototype: `__int64 __fastcall(CSTATPROPBAGArray *__hidden this, unsigned int, struct tagSTATPROPBAG *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055710`
- `0x180056380`

## callees

- `0x1800557bc`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180055846`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180055846`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005585d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005585d`

## pseudocode

```c
__int64 __fastcall CSTATPROPBAGArray::NextAt(
        CSTATPROPBAGArray *this,
        int a2,
        struct tagSTATPROPBAG *a3,
        unsigned int *a4)
{
  __int64 v5; // rcx
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // r15d
  unsigned int v12; // esi
  wchar_t *v13; // r8
  const wchar_t *v14; // rdx
  wchar_t *v15; // rax
  int v16; // eax
  __int16 v17; // ax
  __int64 v18; // rcx
  int v19; // eax
  bool v20; // zf
  wchar_t *Str[2]; // [rsp+30h] [rbp-48h] BYREF

  v5 = *((_QWORD *)this + 2);
  *(_OWORD *)Str = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, 0xFFFFFFFFLL);
  v9 = *((_QWORD *)this + 1);
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
    if ( v10 >= 0 )
    {
      v11 = 0;
      v12 = 0;
      while ( 1 )
      {
        v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **))(**((_QWORD **)this + 1) + 24LL))(
                *((_QWORD *)this + 1),
                1,
                Str);
        v10 = v19;
        if ( v19 )
          break;
        if ( v12 >= *a4 )
          goto LABEL_16;
        v13 = Str[0];
        if ( Str[0] )
        {
          v14 = (const wchar_t *)*((_QWORD *)this + 3);
          if ( !v14
            || (v15 = wcsstr(Str[0], v14), v13 = Str[0], Str[0] == v15)
            || (v16 = lstrcmpW(Str[0], *((LPCWSTR *)this + 3)), v13 = Str[0], !v16) )
          {
            if ( a2 == v11 )
            {
              v17 = WORD2(Str[1]);
              ++a2;
              v18 = 32LL * v12;
              *(_QWORD *)((char *)a3 + v18) = v13;
              v13 = 0;
              *(_WORD *)((char *)a3 + v18 + 8) = v17;
              ++v12;
              Str[0] = 0;
              *(GUID *)((char *)a3 + v18 + 12) = GUID_NULL;
            }
            ++v11;
          }
        }
        CoTaskMemFree(v13);
        Str[0] = 0;
      }
      if ( v19 < 0 )
        goto LABEL_17;
LABEL_16:
      v20 = v12 == *a4;
      *a4 = v12;
      v10 = !v20;
    }
  }
  else
  {
    v10 = 1;
    *a4 = 0;
  }
LABEL_17:
  CoTaskMemFree(Str[0]);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800557bc  push    rbx
0x1800557be  push    rbp
0x1800557bf  push    rsi
0x1800557c0  push    r12
0x1800557c2  push    r13
0x1800557c4  push    r14
0x1800557c6  push    r15
0x1800557c8  sub     rsp, 40h
0x1800557cc  mov     rbp, rcx
0x1800557cf  xorps   xmm0, xmm0
0x1800557d2  mov     rcx, [rcx+10h]
0x1800557d6  mov     r12d, edx
0x1800557d9  movups  xmmword ptr [rsp+78h+Str], xmm0
0x1800557de  or      edx, 0FFFFFFFFh
0x1800557e1  mov     r14, r9
0x1800557e4  mov     r13, r8
0x1800557e7  mov     rax, [rcx]
0x1800557ea  mov     rax, [rax+18h]
0x1800557ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557f3  mov     rcx, [rbp+8]
0x1800557f7  test    rcx, rcx
0x1800557fa  jnz     short loc_180055807
0x1800557fc  lea     ebx, [rcx+1]
0x1800557ff  mov     [r14], ecx
0x180055802  jmp     loc_1800558EB
0x180055807  mov     rax, [rcx]
0x18005580a  mov     rax, [rax+28h]
0x18005580e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055813  mov     ebx, eax
0x180055815  test    eax, eax
0x180055817  js      loc_1800558EB
0x18005581d  xor     r15d, r15d
0x180055820  xor     esi, esi
0x180055822  jmp     loc_1800558B6
0x180055827  cmp     esi, [r14]
0x18005582a  jnb     loc_1800558E0
0x180055830  mov     r8, [rsp+78h+Str]
0x180055835  test    r8, r8
0x180055838  jz      short loc_1800558A4
0x18005583a  mov     rdx, [rbp+18h]; SubStr
0x18005583e  test    rdx, rdx
0x180055841  jz      short loc_18005586C
0x180055843  mov     rcx, r8; Str
0x180055846  call    cs:__imp_wcsstr
0x18005584c  mov     r8, [rsp+78h+Str]
0x180055851  cmp     r8, rax
0x180055854  jz      short loc_18005586C
0x180055856  mov     rdx, [rbp+18h]; lpString2
0x18005585a  mov     rcx, r8; lpString1
0x18005585d  call    cs:__imp_lstrcmpW
0x180055863  mov     r8, [rsp+78h+Str]
0x180055868  test    eax, eax
0x18005586a  jnz     short loc_1800558A4
0x18005586c  cmp     r12d, r15d
0x18005586f  jnz     short loc_1800558A1
0x180055871  movzx   eax, word ptr [rsp+78h+Str+0Ch]
0x180055876  inc     r12d
0x180055879  mov     ecx, esi
0x18005587b  shl     rcx, 5
0x18005587f  mov     [rcx+r13], r8
0x180055883  xor     r8d, r8d
0x180055886  mov     [rcx+r13+8], ax
0x18005588c  inc     esi
0x18005588e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180055895  mov     [rsp+78h+Str], r8
0x18005589a  movdqu  xmmword ptr [rcx+r13+0Ch], xmm0
0x1800558a1  inc     r15d
0x1800558a4  mov     rcx, r8; pv
0x1800558a7  call    cs:__imp_CoTaskMemFree
0x1800558ad  mov     [rsp+78h+Str], 0
0x1800558b6  mov     rcx, [rbp+8]
0x1800558ba  lea     r8, [rsp+78h+Str]
0x1800558bf  xor     r9d, r9d
0x1800558c2  mov     rax, [rcx]
0x1800558c5  lea     edx, [r9+1]
0x1800558c9  mov     rax, [rax+18h]
0x1800558cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558d2  mov     ebx, eax
0x1800558d4  test    eax, eax
0x1800558d6  jz      loc_180055827
0x1800558dc  test    eax, eax
0x1800558de  js      short loc_1800558EB
0x1800558e0  xor     ebx, ebx
0x1800558e2  cmp     esi, [r14]
0x1800558e5  mov     [r14], esi
0x1800558e8  setnz   bl
0x1800558eb  mov     rcx, [rsp+78h+Str]; pv
0x1800558f0  call    cs:__imp_CoTaskMemFree
0x1800558f6  mov     rcx, [rbp+10h]
0x1800558fa  mov     rax, [rcx]
0x1800558fd  mov     rax, [rax+20h]
0x180055901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055906  mov     eax, ebx
0x180055908  add     rsp, 40h
0x18005590c  pop     r15
0x18005590e  pop     r14
0x180055910  pop     r13
0x180055912  pop     r12
0x180055914  pop     rsi
0x180055915  pop     rbp
0x180055916  pop     rbx
0x180055917  retn
```
