# CTimeEnumTypeList::_EnsureTimePointComputed(uint)

- ea: `0x180021374`
- end: `0x1800216b9`
- name: `?_EnsureTimePointComputed@CTimeEnumTypeList@@AEAAJI@Z`
- size: `837`
- prototype: `__int64 __fastcall(CTimeEnumTypeList *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020d20`
- `0x180081b80`

## callees

- `0x180009240`
- `0x180021374`
- `0x1800231e8`
- `0x180023708`
- `0x180065b84`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800215e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021634`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800215e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002154b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002154b`

## pseudocode

```c
__int64 __fastcall CTimeEnumTypeList::_EnsureTimePointComputed(CTimeEnumTypeList *this, unsigned int a2)
{
  HRESULT v2; // ebx
  __int64 v3; // rsi
  _DWORD *v5; // rax
  __int64 v6; // rax
  __int64 v8; // rdi
  int v9; // ecx
  HRESULT v10; // eax
  __int64 v11; // [rsp+30h] [rbp-39h] BYREF
  __int64 v12; // [rsp+38h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  __int64 v14; // [rsp+48h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  LPVOID v16; // [rsp+58h] [rbp-11h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v18; // [rsp+70h] [rbp+7h]
  PROPVARIANT ppropvarDest[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+88h] [rbp+1Fh]
  __int128 v21; // [rsp+90h] [rbp+27h] BYREF
  int v22; // [rsp+A0h] [rbp+37h]

  v2 = 0;
  v3 = a2;
  if ( !*((_DWORD *)this + 26) )
  {
    v5 = (_DWORD *)*((_QWORD *)this + 18);
    if ( !*(_QWORD *)&v5[2 * a2] )
    {
      if ( !a2 )
      {
        *v5 = 711573504;
        *(_DWORD *)(*((_QWORD *)this + 18) + 4LL) = 201;
        return (unsigned int)v2;
      }
      v6 = *(_QWORD *)this;
      v12 = 0;
      v2 = (*(__int64 (__fastcall **)(CTimeEnumTypeList *, _QWORD, GUID *, __int64 *))(v6 + 40))(
             this,
             a2,
             &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea,
             &v12);
      if ( v2 >= 0 )
      {
        v16 = 0;
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v12 + 64LL))(v12, 0, &v16);
        if ( v2 < 0 )
        {
LABEL_17:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          return (unsigned int)v2;
        }
        pv = 0;
        v2 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v12 + 64LL))(v12, 1, &pv);
        if ( v2 < 0 )
        {
LABEL_16:
          CoTaskMemFree(v16);
          goto LABEL_17;
        }
        v14 = 0;
        v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 88LL))(v12, &v14);
        if ( v2 < 0 )
        {
LABEL_15:
          CoTaskMemFree(pv);
          goto LABEL_16;
        }
        v13 = 0;
        if ( (unsigned int)(v3 + 1) < *((_DWORD *)this + 32) || *((_DWORD *)this + 27) )
        {
          v11 = 0;
          v2 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v14 + 72LL))(
                 v14,
                 &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                 &v11);
          if ( v2 < 0 )
            goto LABEL_14;
          v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v11 + 32LL))(
                 v11,
                 0,
                 &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                 &v13);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        else
        {
          v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(
                 v14,
                 &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                 &v13);
        }
        if ( v2 >= 0 )
        {
          v22 = 0;
          LODWORD(v11) = 0;
          v18 = 0;
          v21 = 0;
          *(_OWORD *)pvar = 0;
          v2 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, PROPVARIANT *))(*(_QWORD *)v13 + 128LL))(
                 v13,
                 &v21,
                 &v11,
                 pvar);
          if ( v2 < 0 )
          {
LABEL_13:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            goto LABEL_14;
          }
          v8 = *((_QWORD *)this + 18) + 8 * v3;
          if ( LOWORD(pvar[0]) == 7 )
          {
            v10 = ConvertTimeHelper((FILETIME *)&pvar[1]);
          }
          else
          {
            if ( LOWORD(pvar[0]) == 8 || LOWORD(pvar[0]) == 30 || (v9 = LOWORD(pvar[0]) - 31, LOWORD(pvar[0]) == 31) )
            {
              v20 = 0;
              *(_OWORD *)ppropvarDest = 0;
              v2 = PropVariantChangeType(ppropvarDest, pvar, 0, 0x40u);
              if ( v2 >= 0 )
              {
                v2 = SHConvertTime(&ppropvarDest[1], 256, v8, 0);
                PropVariantClear(ppropvarDest);
              }
              goto LABEL_26;
            }
            if ( LOWORD(pvar[0]) != 64 )
            {
              v2 = -2147024809;
LABEL_26:
              if ( ((__int64)pvar[0] & 0xFFBF) != 0 && (byte_1800F1382 & 0x10) != 0 )
                McTemplateU0hhq_EtwEventWriteTransfer(
                  v9,
                  (unsigned int)ShellTraceId_Properties_PropVariantHelper_Coercion_Info,
                  LOWORD(pvar[0]),
                  64,
                  v2);
              PropVariantClear(pvar);
              goto LABEL_13;
            }
            v10 = SHConvertTime(&pvar[1], 256, v8, 256);
          }
          v2 = v10;
          goto LABEL_26;
        }
LABEL_14:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        goto LABEL_15;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180021374  mov     [rsp-8+arg_10], rbx
0x180021379  mov     [rsp-8+arg_18], rsi
0x18002137e  push    rbp
0x18002137f  push    rdi
0x180021380  push    r14
0x180021382  lea     rbp, [rsp-47h]
0x180021387  sub     rsp, 0B0h
0x18002138e  mov     rax, cs:__security_cookie
0x180021395  xor     rax, rsp
0x180021398  mov     [rbp+57h+var_18], rax
0x18002139c  xor     ebx, ebx
0x18002139e  mov     esi, edx
0x1800213a0  mov     rdi, rcx
0x1800213a3  cmp     [rcx+68h], ebx
0x1800213a6  jnz     loc_180021561
0x1800213ac  mov     rax, [rcx+90h]
0x1800213b3  cmp     [rax+rsi*8], ebx
0x1800213b6  jnz     loc_180021561
0x1800213bc  cmp     [rax+rsi*8+4], ebx
0x1800213c0  jnz     loc_180021561
0x1800213c6  test    edx, edx
0x1800213c8  jz      loc_18002165A
0x1800213ce  mov     rax, [rcx]
0x1800213d1  lea     r9, [rbp+57h+var_88]
0x1800213d5  lea     r8, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea
0x1800213dc  mov     [rbp+57h+var_88], rbx
0x1800213e0  mov     edx, esi
0x1800213e2  mov     rax, [rax+28h]
0x1800213e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213eb  mov     ebx, eax
0x1800213ed  test    eax, eax
0x1800213ef  js      loc_180021561
0x1800213f5  mov     rcx, [rbp+57h+var_88]
0x1800213f9  lea     r8, [rbp+57h+var_68]
0x1800213fd  mov     [rbp+57h+var_68], 0
0x180021405  xor     edx, edx
0x180021407  mov     rax, [rcx]
0x18002140a  mov     rax, [rax+40h]
0x18002140e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021413  mov     ebx, eax
0x180021415  test    eax, eax
0x180021417  js      loc_180021551
0x18002141d  mov     rcx, [rbp+57h+var_88]
0x180021421  lea     r8, [rbp+57h+pv]
0x180021425  mov     [rbp+57h+pv], 0
0x18002142d  mov     edx, 1
0x180021432  mov     rax, [rcx]
0x180021435  mov     rax, [rax+40h]
0x180021439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002143e  mov     ebx, eax
0x180021440  test    eax, eax
0x180021442  js      loc_180021547
0x180021448  mov     rcx, [rbp+57h+var_88]
0x18002144c  lea     rdx, [rbp+57h+var_78]
0x180021450  mov     [rbp+57h+var_78], 0
0x180021458  mov     rax, [rcx]
0x18002145b  mov     rax, [rax+58h]
0x18002145f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021464  mov     ebx, eax
0x180021466  test    eax, eax
0x180021468  js      loc_18002153D
0x18002146e  lea     eax, [rsi+1]
0x180021471  mov     [rbp+57h+var_80], 0
0x180021479  cmp     eax, [rdi+80h]
0x18002147f  jnb     loc_180021673
0x180021485  mov     rcx, [rbp+57h+var_78]
0x180021489  lea     r8, [rbp+57h+var_90]
0x18002148d  mov     [rbp+57h+var_90], 0
0x180021495  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18002149c  mov     rax, [rcx]
0x18002149f  mov     rax, [rax+48h]
0x1800214a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214a8  mov     ebx, eax
0x1800214aa  test    eax, eax
0x1800214ac  js      short loc_18002152D
0x1800214ae  mov     rcx, [rbp+57h+var_90]
0x1800214b2  lea     r9, [rbp+57h+var_80]
0x1800214b6  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800214bd  xor     edx, edx
0x1800214bf  mov     rax, [rcx]
0x1800214c2  mov     rax, [rax+20h]
0x1800214c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214cb  mov     rcx, [rbp+57h+var_90]
0x1800214cf  mov     ebx, eax
0x1800214d1  mov     rax, [rcx]
0x1800214d4  mov     rax, [rax+10h]
0x1800214d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214dd  test    ebx, ebx
0x1800214df  js      short loc_18002152D
0x1800214e1  mov     rcx, [rbp+57h+var_80]
0x1800214e5  lea     r9, [rbp+57h+pvar]
0x1800214e9  xor     eax, eax
0x1800214eb  lea     r8, [rbp+57h+var_90]
0x1800214ef  xorps   xmm0, xmm0
0x1800214f2  mov     [rbp+57h+var_20], eax
0x1800214f5  mov     dword ptr [rbp+57h+var_90], eax
0x1800214f8  lea     rdx, [rbp+57h+var_30]
0x1800214fc  mov     [rbp+57h+var_50], rax
0x180021500  movups  [rbp+57h+var_30], xmm0
0x180021504  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180021508  mov     rax, [rcx]
0x18002150b  mov     rax, [rax+80h]
0x180021512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021517  mov     ebx, eax
0x180021519  test    eax, eax
0x18002151b  jns     short loc_180021587
0x18002151d  mov     rcx, [rbp+57h+var_80]
0x180021521  mov     rax, [rcx]
0x180021524  mov     rax, [rax+10h]
0x180021528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002152d  mov     rcx, [rbp+57h+var_78]
0x180021531  mov     rax, [rcx]
0x180021534  mov     rax, [rax+10h]
0x180021538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002153d  mov     rcx, [rbp+57h+pv]; pv
0x180021541  call    cs:__imp_CoTaskMemFree
0x180021547  mov     rcx, [rbp+57h+var_68]; pv
0x18002154b  call    cs:__imp_CoTaskMemFree
0x180021551  mov     rcx, [rbp+57h+var_88]
0x180021555  mov     rax, [rcx]
0x180021558  mov     rax, [rax+10h]
0x18002155c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021561  mov     eax, ebx
0x180021563  mov     rcx, [rbp+57h+var_18]
0x180021567  xor     rcx, rsp; StackCookie
0x18002156a  call    __security_check_cookie
0x18002156f  lea     r11, [rsp+0C0h+var_10]
0x180021577  mov     rbx, [r11+30h]
0x18002157b  mov     rsi, [r11+38h]
0x18002157f  mov     rsp, r11
0x180021582  pop     r14
0x180021584  pop     rdi
0x180021585  pop     rbp
0x180021586  retn
0x180021587  mov     rax, [rdi+90h]
0x18002158e  movzx   ecx, word ptr [rbp+57h+pvar]
0x180021592  lea     rdi, [rax+rsi*8]
0x180021596  mov     esi, 40h ; '@'
0x18002159b  sub     ecx, 7
0x18002159e  jz      loc_18002169E
0x1800215a4  sub     ecx, 1
0x1800215a7  jz      short loc_1800215F4
0x1800215a9  sub     ecx, 16h
0x1800215ac  jz      short loc_1800215F4
0x1800215ae  sub     ecx, 1
0x1800215b1  jz      short loc_1800215F4
0x1800215b3  cmp     ecx, 21h ; '!'
0x1800215b6  jnz     short loc_1800215ED
0x1800215b8  mov     edx, 100h
0x1800215bd  lea     rcx, [rbp+57h+pvar+8]
0x1800215c1  mov     r9d, edx
0x1800215c4  mov     r8, rdi
0x1800215c7  call    ?SHConvertTime@@YAJPEBU_FILETIME@@W4SHTIME_FLAGS@@PEAU1@1@Z; SHConvertTime(_FILETIME const *,SHTIME_FLAGS,_FILETIME *,SHTIME_FLAGS)
0x1800215cc  mov     ebx, eax
0x1800215ce  movzx   r8d, word ptr [rbp+57h+pvar]
0x1800215d3  mov     eax, 0FFBFh
0x1800215d8  test    ax, r8w
0x1800215dc  jnz     short loc_18002163C
0x1800215de  lea     rcx, [rbp+57h+pvar]; pvar
0x1800215e2  call    cs:__imp_PropVariantClear
0x1800215e8  jmp     loc_18002151D
0x1800215ed  mov     ebx, 80070057h
0x1800215f2  jmp     short loc_1800215CE
0x1800215f4  xorps   xmm0, xmm0
0x1800215f7  lea     rdx, [rbp+57h+pvar]; propvarSrc
0x1800215fb  xor     eax, eax
0x1800215fd  lea     rcx, [rbp+57h+ppropvarDest]; ppropvarDest
0x180021601  mov     r9d, esi; vt
0x180021604  mov     [rbp+57h+var_38], rax
0x180021608  xor     r8d, r8d; flags
0x18002160b  movups  xmmword ptr [rbp+57h+ppropvarDest], xmm0
0x18002160f  call    PropVariantChangeType
0x180021614  mov     ebx, eax
0x180021616  test    eax, eax
0x180021618  js      short loc_1800215CE
0x18002161a  xor     r9d, r9d
0x18002161d  lea     rcx, [rbp+57h+ppropvarDest+8]
0x180021621  mov     r8, rdi
0x180021624  mov     edx, 100h
0x180021629  call    ?SHConvertTime@@YAJPEBU_FILETIME@@W4SHTIME_FLAGS@@PEAU1@1@Z; SHConvertTime(_FILETIME const *,SHTIME_FLAGS,_FILETIME *,SHTIME_FLAGS)
0x18002162e  lea     rcx, [rbp+57h+ppropvarDest]; pvar
0x180021632  mov     ebx, eax
0x180021634  call    cs:__imp_PropVariantClear
0x18002163a  jmp     short loc_1800215CE
0x18002163c  test    cs:byte_1800F1382, 10h
0x180021643  jz      short loc_1800215DE
0x180021645  mov     r9d, esi
0x180021648  mov     [rsp+0C0h+var_A0], ebx
0x18002164c  lea     rdx, ShellTraceId_Properties_PropVariantHelper_Coercion_Info
0x180021653  call    McTemplateU0hhq_EtwEventWriteTransfer
0x180021658  jmp     short loc_1800215DE
0x18002165a  mov     dword ptr [rax], 2A69C000h
0x180021660  mov     rax, [rcx+90h]
0x180021667  mov     dword ptr [rax+4], 0C9h
0x18002166e  jmp     loc_180021561
0x180021673  cmp     dword ptr [rdi+6Ch], 0
0x180021677  jnz     loc_180021485
0x18002167d  mov     rcx, [rbp+57h+var_78]
0x180021681  lea     r8, [rbp+57h+var_80]
0x180021685  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18002168c  mov     rax, [rcx]
0x18002168f  mov     rax, [rax]
0x180021692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021697  mov     ebx, eax
0x180021699  jmp     loc_1800214DD
0x18002169e  mov     r9d, 101h
0x1800216a4  lea     rcx, [rbp+57h+pvar+8]; lpFileTime
0x1800216a8  mov     r8, rdi
0x1800216ab  lea     edx, [r9+2]
0x1800216af  call    _ConvertTimeHelper
0x1800216b4  jmp     loc_1800215CC
```
