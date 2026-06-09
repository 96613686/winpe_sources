# DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)

- ea: `0x1800327fc`
- end: `0x180032efa`
- name: `?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z`
- size: `1790`
- prototype: `__int64 __fastcall(unsigned __int64, struct tagVARIANT *, void (__fastcall **)(struct Js::ScriptContext *))`
- caller_count: `8`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18001ff78`
- `0x180031140`
- `0x18010d0b0`
- `0x180134008`
- `0x180172940`
- `0x1801d3d18`
- `0x1801f9708`
- `0x1801fd9f0`

## callees

- `0x180004958`
- `0x1800327fc`
- `0x1800339e0`
- `0x180033a50`
- `0x180064f20`
- `0x180141b44`
- `0x18017fac8`
- `0x180181384`
- `0x18019bca4`
- `0x1801a742c`
- `0x180364010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180032a4f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180032abd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180032a4f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180032abd`
- `KERNEL32!GetTickCount` at `0x1800328c9`
- `KERNEL32!GetTickCount` at `0x180032ad5`
- `KERNEL32!GetTickCount` at `0x1800328c9`
- `KERNEL32!GetTickCount` at `0x180032ad5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180032b43`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180032b43`
- `OLEAUT32!__imp_VariantInit` at `0x18003293b`
- `OLEAUT32!__imp_VariantInit` at `0x18003293b`
- `OLEAUT32!__imp_VariantCopy` at `0x180032dd7`
- `OLEAUT32!__imp_VariantCopy` at `0x180032dd7`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180032df3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180032df3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DispatchHelper::MarshalJsVarToVariantNoThrow(
        unsigned __int64 a1,
        struct tagVARIANT *a2,
        void (__fastcall **a3)(struct Js::ScriptContext *))
{
  int v3; // r15d
  void (__fastcall *v5)(struct Js::ScriptContext *); // rbx
  __int64 v6; // rsi
  int v7; // ecx
  _DWORD *v8; // rax
  void (__fastcall *v9)(struct Js::ScriptContext *); // rax
  void (__fastcall *v10)(struct Js::ScriptContext *); // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  void (__fastcall *v17)(struct Js::ScriptContext *); // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rdi
  DWORD TickCount; // eax
  int v25; // ecx
  int v26; // ecx
  UINT v27; // esi
  const OLECHAR *OriginalStringReference; // rax
  BSTR v29; // rax
  VARTYPE v30; // ax
  double v31; // xmm0_8
  __int64 v32; // rcx
  void (__fastcall *v33)(struct Js::ScriptContext *); // rax
  unsigned int v34; // eax
  __int64 v35; // rcx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  struct IDispatch *Dispatch; // rax
  const VARIANTARG *v44; // rdx
  int v45; // ecx
  int v46; // ecx
  bool v47; // zf
  int v48; // ecx
  int v49; // ecx
  bool v50; // zf
  bool v51; // zf
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  struct Js::RecyclableObject *v57; // r8
  int TypeId; // eax
  char v59; // [rsp+20h] [rbp-98h]
  __int64 v60; // [rsp+28h] [rbp-90h] BYREF
  _QWORD v61[4]; // [rsp+30h] [rbp-88h] BYREF
  _DWORD *v62; // [rsp+50h] [rbp-68h]
  _QWORD *v63; // [rsp+58h] [rbp-60h]
  __int16 v64; // [rsp+60h] [rbp-58h]
  char v65; // [rsp+62h] [rbp-56h]
  void (__fastcall **v66)(struct Js::ScriptContext *); // [rsp+68h] [rbp-50h]
  __int64 v67; // [rsp+70h] [rbp-48h]
  unsigned __int64 *v68; // [rsp+78h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+0h]

  v67 = -2;
  try
  {
    v3 = 0;
    v61[0] = 0;
    v61[2] = 0;
    v62 = 0;
    v66 = a3;
    v63 = v61;
    v64 = 0;
    v59 = *((_BYTE *)a3 + 3136);
    v65 = v59;
    v61[1] = retaddr;
    v61[3] = a3;
    v5 = a3[148];
    v6 = *((_QWORD *)v5 + 72);
    if ( (byte_18043FDC1 & 0x10) != 0 )
      McTemplateU0pq_EventWriteTransfer((int)&BERP_IE_Context, (int)JSCRIPT_RUN_START, (__int64)a3[148], 0);
    v7 = *((_DWORD *)v5 + 22);
    *((_DWORD *)v5 + 22) = v7 + 1;
    if ( !v7 )
    {
      GetSystemTimeAsFileTime(*((LPFILETIME *)v5 + 1738));
      v23 = *((_QWORD *)v5 + 1745);
      if ( v23 )
      {
        TickCount = GetTickCount();
        *(_DWORD *)(v23 + 16) = TickCount;
        *(_DWORD *)(v23 + 20) = TickCount;
      }
      *(_BYTE *)(v6 + 12896) = 1;
    }
    v8 = (_DWORD *)*((_QWORD *)v5 + 78);
    if ( v8 )
    {
      *v8 |= 2u;
      v62 = v8;
    }
    *((_QWORD *)v5 + 78) = v61;
    *((_BYTE *)v5 + 8849) = 1;
    *(_BYTE *)(v6 + 12895) = 1;
    *(_DWORD *)(v6 + 12884) = GetTickCount() + 300;
    v9 = a3[337];
    if ( v9 && *((_BYTE *)a3 + 3136) )
    {
      *((_BYTE *)a3 + 3136) = 0;
      v9((struct Js::ScriptContext *)a3);
    }
    v10 = a3[297];
    if ( v10 )
    {
      v11 = *((_QWORD *)v10 + 9);
      if ( *(_DWORD *)(*(_QWORD *)(v11 + 1184) + 88LL) <= 2u
        && (unsigned int)(*((_DWORD *)v10 + 22) - 1) <= 0x1E
        && !*((_BYTE *)v10 + 117)
        && (*(_DWORD *)(v11 + 1196) != 2 || !byte_180442DB0) )
      {
        v34 = *(_DWORD *)(v11 + 3144);
        if ( v34 < 3 )
        {
          *(_DWORD *)(v11 + 3144) = v34 + 1;
          if ( !*(_BYTE *)(*((_QWORD *)v10 + 9) + 2748LL) )
          {
            v60 = 0;
            if ( (byte_18043FDC1 & 8) != 0 )
              McTemplateU0pq_EventWriteTransfer(
                (int)&BERP_IE_Context,
                (int)JSCRIPT_NATIVECODEGEN_DELAY_START,
                (__int64)&v60,
                0);
            v35 = *((_QWORD *)v10 + 3);
            if ( *(_BYTE *)(v35 + 8) )
              JsUtil::BackgroundJobProcessor::PrioritizeManagerAndWait<NativeCodeGenerator>(
                (struct JsUtil::Job **)v35,
                (__int64)v10);
            else
              JsUtil::ForegroundJobProcessor::PrioritizeManagerAndWait<NativeCodeGenerator>(
                (JsUtil::JobProcessor *)v35,
                (struct JsUtil::JobManager *)v10);
            if ( (byte_18043FDC1 & 8) != 0 )
              McTemplateU0pq_EventWriteTransfer(
                (int)&BERP_IE_Context,
                (int)JSCRIPT_NATIVECODEGEN_DELAY_STOP,
                (__int64)&v60,
                0);
          }
        }
      }
    }
    VariantInit(a2);
    if ( !a1 )
      goto LABEL_33;
    if ( HIWORD(a1) == 1 )
    {
LABEL_26:
      a2->vt = 3;
      a2->lVal = a1;
      goto LABEL_27;
    }
    if ( a1 >= 0x4000000000000LL )
      goto LABEL_43;
    v12 = *(_QWORD *)(a1 + 8);
    v13 = *(_DWORD *)v12;
    if ( *(int *)v12 > 26 )
    {
      if ( v13 <= 40 )
      {
        if ( v13 == 40 )
          goto LABEL_78;
        if ( v13 <= 34 )
        {
          if ( v13 == 34 )
            goto LABEL_78;
          v53 = v13 - 27;
          if ( !v53 )
            goto LABEL_78;
          v54 = v53 - 1;
          if ( !v54 )
            goto LABEL_78;
          v55 = v54 - 1;
          if ( !v55 )
            goto LABEL_78;
          v56 = v55 - 1;
          if ( !v56 )
            goto LABEL_78;
          v39 = v56 - 2;
          v50 = v39 == 0;
          goto LABEL_105;
        }
        v52 = v13 - 35;
        v51 = v52 == 0;
      }
      else
      {
        if ( v13 > 46 )
        {
          v36 = v13 - 47;
          if ( !v36 )
            goto LABEL_78;
          v37 = v36 - 1;
          if ( !v37 )
            goto LABEL_78;
          v38 = v37 - 1;
          if ( !v38 )
            goto LABEL_78;
          v39 = v38 - 1;
          if ( !v39 )
            goto LABEL_77;
LABEL_76:
          if ( v39 != 1 )
            goto LABEL_77;
          goto LABEL_78;
        }
        if ( v13 == 46 )
          goto LABEL_78;
        v52 = v13 - 41;
        v51 = v52 == 0;
      }
    }
    else
    {
      if ( v13 == 26 )
        goto LABEL_78;
      if ( v13 <= 12 )
      {
        if ( v13 != 12 )
        {
          if ( v13 <= 6 )
          {
            if ( v13 == 6 )
            {
              a2->vt = 5;
              v32 = *(_QWORD *)(a1 + 16);
              if ( v32 < 0 )
                v31 = (double)(int)(v32 & 1 | ((unsigned __int64)v32 >> 1))
                    + (double)(int)(v32 & 1 | ((unsigned __int64)v32 >> 1));
              else
                v31 = (double)(int)v32;
              goto LABEL_53;
            }
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( !v15 )
                {
                  a2->vt = 11;
                  a2->iVal = -(*(_DWORD *)(a1 + 16) != 0);
                  goto LABEL_27;
                }
                v16 = v15 - 1;
                if ( !v16 )
                  goto LABEL_26;
                v25 = v16 - 1;
                if ( !v25 )
                {
LABEL_43:
                  a2->vt = 5;
                  a2->llVal = a1 ^ 0xFFFC000000000000uLL;
                  goto LABEL_27;
                }
                if ( v25 == 1 )
                {
                  a2->vt = 5;
                  v31 = (double)(int)*(_QWORD *)(a1 + 16);
LABEL_53:
                  a2->dblVal = v31;
                  goto LABEL_27;
                }
                goto LABEL_77;
              }
LABEL_33:
              a2->vt = 1;
              goto LABEL_27;
            }
            v30 = 0;
LABEL_50:
            a2->vt = v30;
            goto LABEL_27;
          }
          v26 = v13 - 7;
          if ( !v26 )
          {
            if ( a1 == *(_QWORD *)(*(_QWORD *)(v12 + 8) + 3224LL) )
            {
              a2->llVal = 0;
            }
            else
            {
              v27 = *(_DWORD *)(a1 + 16);
              OriginalStringReference = (const OLECHAR *)Js::JavascriptString::GetOriginalStringReference((Js::JavascriptString *)a1);
              v29 = SysAllocStringLen(OriginalStringReference, v27);
              a2->llVal = (LONGLONG)v29;
              if ( !v29 )
                v3 = -2147024882;
            }
            a2->vt = 8;
            goto LABEL_27;
          }
          v40 = v26 - 1;
          if ( v40 )
          {
            v41 = v40 - 1;
            if ( !v41 )
            {
              v3 = SafeArrayCopy(*(SAFEARRAY **)(a1 + 24), &a2->parray);
              if ( v3 < 0 )
                goto LABEL_27;
              v30 = *(_WORD *)(a1 + 16);
              goto LABEL_50;
            }
            v42 = v41 - 1;
            if ( !v42 )
            {
              a2->vt = 7;
              Dispatch = *(struct IDispatch **)(a1 + 16);
LABEL_91:
              a2->llVal = (LONGLONG)Dispatch;
              goto LABEL_27;
            }
            if ( v42 == 1 )
            {
              Dispatch = HostDispatch::GetDispatch((HostDispatch *)a1);
              if ( !Dispatch )
              {
                v44 = (const VARIANTARG *)((*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 16LL)
                                         & -(__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) != 0));
                if ( v44 )
                  v3 = VariantCopy(a2, v44);
                else
                  v3 = MapHr(0x80070005, 0);
                goto LABEL_27;
              }
              a2->vt = 9;
              goto LABEL_91;
            }
          }
LABEL_77:
          if ( (*(unsigned int (__fastcall **)(unsigned __int64))(*(_QWORD *)a1 + 504LL))(a1) )
            goto LABEL_78;
          v3 = -2147467263;
LABEL_27:
          if ( v59 )
          {
            v33 = a3[338];
            if ( v33 )
              v33((struct Js::ScriptContext *)a3);
          }
          v17 = a3[148];
          *((_QWORD *)v17 + 78) = *(_QWORD *)(*((_QWORD *)v17 + 78) + 32LL);
          *((_BYTE *)v17 + 8849) = 0;
          *(_BYTE *)(*((_QWORD *)v17 + 72) + 12895LL) = 0;
          v47 = (*((_DWORD *)v17 + 22))-- == 1;
          if ( v47 )
          {
            GetSystemTimeAsFileTime((LPFILETIME)(*((_QWORD *)v17 + 1738) + 8LL));
            *(_BYTE *)(*((_QWORD *)v17 + 72) + 12896LL) = 0;
            v19 = *((_QWORD *)v17 + 1745);
            if ( v19 )
              *(_QWORD *)(v19 + 16) = 0;
            ThreadContext::ClosePendingProjectionContexts((ThreadContext *)v17);
            ThreadContext::ClosePendingScriptContexts((ThreadContext *)v17);
            v20 = *((_QWORD *)v17 + 228);
            v21 = *(_QWORD *)(v20 + 472);
            *(_QWORD *)(v20 + 472) = 0;
            while ( v21 )
            {
              v22 = (_QWORD *)(v21 + 208);
              v21 = *(_QWORD *)(v21 + 208);
              *v22 = 0;
            }
          }
          if ( (byte_18043FDC1 & 0x10) != 0 )
            McTemplateU0pq_EventWriteTransfer((int)&BERP_IE_Context, (int)JSCRIPT_RUN_STOP, (__int64)v17, 0);
          LODWORD(v60) = v3;
          return (unsigned int)v60;
        }
LABEL_78:
        DispatchHelper::MarshalJsVarToDispatchVariant((void *)a1, a2);
        goto LABEL_27;
      }
      if ( v13 <= 20 )
      {
        if ( v13 == 20 )
          goto LABEL_78;
        v45 = v13 - 13;
        if ( !v45 )
          goto LABEL_78;
        v46 = v45 - 1;
        if ( !v46 )
          goto LABEL_78;
        v48 = v46 - 2;
        v47 = v48 == 0;
LABEL_102:
        if ( v47 )
          goto LABEL_78;
        v49 = v48 - 1;
        if ( !v49 )
          goto LABEL_78;
        v39 = v49 - 1;
        v50 = v39 == 0;
LABEL_105:
        if ( v50 )
          goto LABEL_78;
        goto LABEL_76;
      }
      v52 = v13 - 21;
      v51 = v52 == 0;
    }
    if ( v51 )
      goto LABEL_78;
    v48 = v52 - 1;
    v47 = v48 == 0;
    goto LABEL_102;
  }
  catch ( Js::InternalErrorException )
  {
    LODWORD(v60) = -2147467259;
    return (unsigned int)v60;
  }
  catch ( Js::OutOfMemoryException )
  {
    LODWORD(v60) = -2147024882;
    return (unsigned int)v60;
  }
  catch ( Js::StackOverflowException )
  {
    LODWORD(v60) = -2146828260;
    return (unsigned int)v60;
  }
  catch ( Js::NotImplementedException )
  {
    LODWORD(v60) = -2147467263;
    return (unsigned int)v60;
  }
  catch ( Js::ScriptAbortException )
  {
    LODWORD(v60) = -2147467260;
    return (unsigned int)v60;
  }
  catch ( Js::JavascriptExceptionObject *v68 )
  {
    if ( *v68
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v68) == 23
       || (TypeId = Js::JavascriptOperators::GetTypeId((unsigned __int64)v57), TypeId == 11)) )
    {
      LODWORD(v60) = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v57, 0);
    }
    else
    {
      LODWORD(v60) = -2147024882;
    }
    return (unsigned int)v60;
  }
  catch ( ... )
  {
    LODWORD(v60) = -2147467259;
  }
  return (unsigned int)v60;
}

```

## disassembly

```asm
0x1800327fc  mov     r11, rsp
0x1800327ff  mov     [r11+18h], r8
0x180032803  mov     [r11+10h], rdx
0x180032807  mov     [r11+8], rcx
0x18003280b  push    rbx
0x18003280c  push    rsi
0x18003280d  push    rdi
0x18003280e  push    r12
0x180032810  push    r13
0x180032812  push    r14
0x180032814  push    r15
0x180032816  sub     rsp, 80h
0x18003281d  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180032825  xor     r15d, r15d
0x180032828  mov     [rsp+0B8h+var_88], r15
0x18003282d  mov     [r11-78h], r15
0x180032831  mov     [r11-68h], r15
0x180032835  mov     rax, [rsp+0B8h]
0x18003283d  mov     r13, r8
0x180032840  mov     [r11-50h], r8
0x180032844  lea     rcx, [rsp+0B8h+var_88]
0x180032849  mov     [r11-60h], rcx
0x18003284d  mov     [r11-58h], r15w
0x180032852  mov     cl, [r8+0C40h]
0x180032859  mov     [rsp+0B8h+var_98], cl
0x18003285d  mov     [rsp+0B8h+var_56], cl
0x180032861  mov     [r11-80h], rax
0x180032865  mov     [r11-70h], r8
0x180032869  mov     rbx, [r8+4A0h]
0x180032870  mov     rsi, [rbx+240h]
0x180032877  test    cs:byte_18043FDC1, 10h
0x18003287e  jnz     loc_180032D0D
0x180032884  mov     ecx, [rbx+58h]
0x180032887  lea     eax, [rcx+1]
0x18003288a  mov     [rbx+58h], eax
0x18003288d  test    ecx, ecx
0x18003288f  jz      loc_180032AB6
0x180032895  mov     r14d, 1
0x18003289b  mov     rax, [rbx+270h]
0x1800328a2  test    rax, rax
0x1800328a5  jz      short loc_1800328AF
0x1800328a7  or      dword ptr [rax], 2
0x1800328aa  mov     [rsp+0B8h+var_68], rax
0x1800328af  lea     rax, [rsp+0B8h+var_88]
0x1800328b4  mov     [rbx+270h], rax
0x1800328bb  mov     [rbx+2291h], r14b
0x1800328c2  mov     [rsi+325Fh], r14b
0x1800328c9  call    cs:__imp_GetTickCount
0x1800328d0  nop     dword ptr [rax+rax+00h]
0x1800328d5  add     eax, 12Ch
0x1800328da  mov     [rsi+3254h], eax
0x1800328e0  mov     rax, [r13+0A88h]
0x1800328e7  test    rax, rax
0x1800328ea  jz      short loc_1800328F9
0x1800328ec  cmp     [r13+0C40h], r15b
0x1800328f3  jnz     loc_180032B9D
0x1800328f9  mov     rbx, [r13+948h]
0x180032900  test    rbx, rbx
0x180032903  jz      short loc_180032925
0x180032905  mov     rcx, [rbx+48h]
0x180032909  mov     rax, [rcx+4A0h]
0x180032910  cmp     dword ptr [rax+58h], 2
0x180032914  ja      short loc_180032925
0x180032916  mov     eax, [rbx+58h]
0x180032919  sub     eax, r14d
0x18003291c  cmp     eax, 1Eh
0x18003291f  jbe     loc_180032BEA
0x180032925  mov     esi, 3
0x18003292a  mov     r12d, 8
0x180032930  mov     rbx, [rsp+0B8h+pvarg]
0x180032938  mov     rcx, rbx; pvarg
0x18003293b  call    cs:__imp_VariantInit
0x180032942  nop     dword ptr [rax+rax+00h]
0x180032947  mov     rdi, [rsp+0B8h+arg_0]
0x18003294f  test    rdi, rdi
0x180032952  jz      loc_180032A3F
0x180032958  mov     rax, rdi
0x18003295b  shr     rax, 30h
0x18003295f  cmp     rax, r14
0x180032962  jz      short loc_1800329CD
0x180032964  mov     rax, 4000000000000h
0x18003296e  cmp     rdi, rax
0x180032971  jnb     loc_180032AFE
0x180032977  mov     rdx, [rdi+8]
0x18003297b  mov     ecx, [rdx]
0x18003297d  cmp     ecx, 1Ah
0x180032980  jg      loc_180032C82
0x180032986  jz      loc_180032CC7
0x18003298c  cmp     ecx, 0Ch
0x18003298f  jg      loc_180032E13
0x180032995  jz      loc_180032CC7
0x18003299b  cmp     ecx, 6
0x18003299e  jg      loc_180032B19
0x1800329a4  jz      loc_180032BB1
0x1800329aa  test    ecx, ecx
0x1800329ac  jz      loc_180032B68
0x1800329b2  sub     ecx, 1
0x1800329b5  jz      loc_180032A3F
0x1800329bb  sub     ecx, 1
0x1800329be  jz      loc_180032C6C
0x1800329c4  sub     ecx, 1
0x1800329c7  jnz     loc_180032AF9
0x1800329cd  mov     [rbx], si
0x1800329d0  mov     [rbx+8], edi
0x1800329d3  cmp     [rsp+0B8h+var_98], 0
0x1800329d8  jnz     loc_180032BCD
0x1800329de  mov     rbx, [r13+4A0h]
0x1800329e5  mov     rax, [rbx+270h]
0x1800329ec  mov     rcx, [rax+20h]
0x1800329f0  mov     [rbx+270h], rcx
0x1800329f7  xor     r13d, r13d
0x1800329fa  mov     [rbx+2291h], r13b
0x180032a01  mov     rax, [rbx+240h]
0x180032a08  mov     [rax+325Fh], r13b
0x180032a0f  add     dword ptr [rbx+58h], 0FFFFFFFFh
0x180032a13  jz      short loc_180032A45
0x180032a15  test    cs:byte_18043FDC1, 10h
0x180032a1c  jnz     loc_180032EB9
0x180032a22  mov     dword ptr [rsp+0B8h+var_90], r15d
0x180032a27  mov     eax, dword ptr [rsp+0B8h+var_90]
0x180032a2b  add     rsp, 80h
0x180032a32  pop     r15
0x180032a34  pop     r14
0x180032a36  pop     r13
0x180032a38  pop     r12
0x180032a3a  pop     rdi
0x180032a3b  pop     rsi
0x180032a3c  pop     rbx
0x180032a3d  retn
0x180032a3f  mov     [rbx], r14w
0x180032a43  jmp     short loc_1800329D3
0x180032a45  mov     rcx, [rbx+3650h]
0x180032a4c  add     rcx, r12; lpSystemTimeAsFileTime
0x180032a4f  call    cs:__imp_GetSystemTimeAsFileTime
0x180032a56  nop     dword ptr [rax+rax+00h]
0x180032a5b  mov     rax, [rbx+240h]
0x180032a62  mov     [rax+3260h], r13b
0x180032a69  mov     rax, [rbx+3688h]
0x180032a70  test    rax, rax
0x180032a73  jz      short loc_180032A79
0x180032a75  mov     [rax+10h], r13
0x180032a79  mov     rcx, rbx; this
0x180032a7c  call    ?ClosePendingProjectionContexts@ThreadContext@@QEAAXXZ; ThreadContext::ClosePendingProjectionContexts(void)
0x180032a81  mov     rcx, rbx; this
0x180032a84  call    ?ClosePendingScriptContexts@ThreadContext@@QEAAXXZ; ThreadContext::ClosePendingScriptContexts(void)
0x180032a89  mov     rax, [rbx+720h]
0x180032a90  mov     rcx, [rax+1D8h]
0x180032a97  mov     [rax+1D8h], r13
0x180032a9e  test    rcx, rcx
0x180032aa1  jz      loc_180032A15
0x180032aa7  lea     rax, [rcx+0D0h]
0x180032aae  mov     rcx, [rax]
0x180032ab1  mov     [rax], r13
0x180032ab4  jmp     short loc_180032A9E
0x180032ab6  mov     rcx, [rbx+3650h]; lpSystemTimeAsFileTime
0x180032abd  call    cs:__imp_GetSystemTimeAsFileTime
0x180032ac4  nop     dword ptr [rax+rax+00h]
0x180032ac9  mov     rdi, [rbx+3688h]
0x180032ad0  test    rdi, rdi
0x180032ad3  jz      short loc_180032AE7
0x180032ad5  call    cs:__imp_GetTickCount
0x180032adc  nop     dword ptr [rax+rax+00h]
0x180032ae1  mov     [rdi+10h], eax
0x180032ae4  mov     [rdi+14h], eax
0x180032ae7  mov     r14d, 1
0x180032aed  mov     [rsi+3260h], r14b
0x180032af4  jmp     loc_18003289B
0x180032af9  sub     ecx, 1
0x180032afc  jnz     short loc_180032B72
0x180032afe  mov     word ptr [rbx], 5
0x180032b03  mov     rax, 0FFFC000000000000h
0x180032b0d  xor     rdi, rax
0x180032b10  mov     [rbx+8], rdi
0x180032b14  jmp     loc_1800329D3
0x180032b19  mov     eax, 7
0x180032b1e  sub     ecx, eax
0x180032b20  jnz     loc_180032D6B
0x180032b26  mov     rax, [rdx+8]
0x180032b2a  cmp     rdi, [rax+0C98h]
0x180032b31  jz      short loc_180032B93
0x180032b33  mov     esi, [rdi+10h]
0x180032b36  mov     rcx, rdi; this
0x180032b39  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x180032b3e  mov     edx, esi; ui
0x180032b40  mov     rcx, rax; strIn
0x180032b43  call    cs:__imp_SysAllocStringLen
0x180032b4a  nop     dword ptr [rax+rax+00h]
0x180032b4f  mov     [rbx+8], rax
0x180032b53  mov     ecx, 8007000Eh
0x180032b58  test    rax, rax
0x180032b5b  cmovz   r15d, ecx
0x180032b5f  mov     [rbx], r12w
0x180032b63  jmp     loc_1800329D3
0x180032b68  xor     eax, eax
0x180032b6a  mov     [rbx], ax
0x180032b6d  jmp     loc_1800329D3
0x180032b72  cmp     ecx, 1
0x180032b75  jnz     loc_180032CAD
0x180032b7b  mov     word ptr [rbx], 5
0x180032b80  xorps   xmm0, xmm0
0x180032b83  cvtsi2sd xmm0, qword ptr [rdi+10h]
0x180032b89  movsd   qword ptr [rbx+8], xmm0
0x180032b8e  jmp     loc_1800329D3
0x180032b93  mov     qword ptr [rbx+8], 0
0x180032b9b  jmp     short loc_180032B5F
0x180032b9d  mov     [r13+0C40h], r15b
0x180032ba4  mov     rcx, r13
0x180032ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bac  jmp     loc_1800328F9
0x180032bb1  mov     word ptr [rbx], 5
0x180032bb6  mov     rcx, [rdi+10h]
0x180032bba  xorps   xmm0, xmm0
0x180032bbd  test    rcx, rcx
0x180032bc0  js      loc_180032CE1
0x180032bc6  cvtsi2sd xmm0, rcx
0x180032bcb  jmp     short loc_180032B89
0x180032bcd  mov     rax, [r13+0A90h]
0x180032bd4  test    rax, rax
0x180032bd7  jz      loc_1800329DE
0x180032bdd  mov     rcx, r13
0x180032be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032be5  jmp     loc_1800329DE
0x180032bea  cmp     [rbx+75h], r15b
0x180032bee  jnz     loc_180032925
0x180032bf4  cmp     dword ptr [rcx+4ACh], 2
0x180032bfb  jz      loc_180032CFB
0x180032c01  mov     eax, [rcx+0C48h]
0x180032c07  mov     esi, 3
0x180032c0c  cmp     eax, esi
0x180032c0e  jnb     loc_18003292A
0x180032c14  inc     eax
0x180032c16  mov     [rcx+0C48h], eax
0x180032c1c  mov     rax, [rbx+48h]
0x180032c20  cmp     [rax+0ABCh], r15b
0x180032c27  jnz     loc_18003292A
0x180032c2d  mov     [rsp+0B8h+var_90], r15
0x180032c32  lea     r12d, [rsi+5]
0x180032c36  test    cs:byte_18043FDC1, r12b
0x180032c3d  jnz     loc_180032D2B
0x180032c43  mov     rcx, [rbx+18h]; this
0x180032c47  mov     rdx, rbx
0x180032c4a  cmp     [rcx+8], r15b
0x180032c4e  jz      loc_180032CD7
0x180032c54  call    ??$PrioritizeManagerAndWait@VNativeCodeGenerator@@@BackgroundJobProcessor@JsUtil@@QEAAXQEAVNativeCodeGenerator@@I@Z; JsUtil::BackgroundJobProcessor::PrioritizeManagerAndWait<NativeCodeGenerator>(NativeCodeGenerator * const,uint)
0x180032c59  nop
0x180032c5a  test    cs:byte_18043FDC1, r12b
0x180032c61  jnz     loc_180032D4B
0x180032c67  jmp     loc_180032930
0x180032c6c  mov     word ptr [rbx], 0Bh
0x180032c71  mov     eax, [rdi+10h]
0x180032c74  neg     eax
0x180032c76  sbb     cx, cx
0x180032c79  mov     [rbx+8], cx
0x180032c7d  jmp     loc_1800329D3
0x180032c82  cmp     ecx, 28h ; '('
0x180032c85  jle     loc_180032E6A
0x180032c8b  cmp     ecx, 2Eh ; '.'
0x180032c8e  jle     loc_180032EA6
0x180032c94  sub     ecx, 2Fh ; '/'
0x180032c97  jz      short loc_180032CC7
0x180032c99  sub     ecx, 1
0x180032c9c  jz      short loc_180032CC7
0x180032c9e  sub     ecx, 1
0x180032ca1  jz      short loc_180032CC7
0x180032ca3  sub     ecx, 1
0x180032ca6  jz      short loc_180032CAD
0x180032ca8  cmp     ecx, 1
0x180032cab  jz      short loc_180032CC7
0x180032cad  mov     rax, [rdi]
0x180032cb0  mov     rcx, rdi
0x180032cb3  mov     rax, [rax+1F8h]
0x180032cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cbf  test    eax, eax
0x180032cc1  jz      loc_180032EAE
0x180032cc7  mov     rdx, rbx; struct tagVARIANT *
0x180032cca  mov     rcx, rdi; void *
0x180032ccd  call    ?MarshalJsVarToDispatchVariant@DispatchHelper@@CAXPEAXPEAUtagVARIANT@@@Z; DispatchHelper::MarshalJsVarToDispatchVariant(void *,tagVARIANT *)
0x180032cd2  jmp     loc_1800329D3
0x180032cd7  call    ??$PrioritizeManagerAndWait@VNativeCodeGenerator@@@ForegroundJobProcessor@JsUtil@@QEAAXQEAVNativeCodeGenerator@@I@Z; JsUtil::ForegroundJobProcessor::PrioritizeManagerAndWait<NativeCodeGenerator>(NativeCodeGenerator * const,uint)
0x180032cdc  jmp     loc_180032C5A
0x180032ce1  mov     rax, rcx
0x180032ce4  shr     rax, 1
0x180032ce7  and     rcx, r14
0x180032cea  or      rax, rcx
0x180032ced  cvtsi2sd xmm0, rax
0x180032cf2  addsd   xmm0, xmm0
0x180032cf6  jmp     loc_180032B89
0x180032cfb  cmp     cs:byte_180442DB0, r15b
0x180032d02  jnz     loc_180032925
0x180032d08  jmp     loc_180032C01
0x180032d0d  xor     r9d, r9d
0x180032d10  mov     r8, rbx
0x180032d13  lea     rdx, JSCRIPT_RUN_START
0x180032d1a  lea     rcx, BERP_IE_Context
0x180032d21  call    McTemplateU0pq_EventWriteTransfer
0x180032d26  jmp     loc_180032884
0x180032d2b  xor     r9d, r9d
0x180032d2e  lea     r8, [rsp+0B8h+var_90]
0x180032d33  lea     rdx, JSCRIPT_NATIVECODEGEN_DELAY_START
0x180032d3a  lea     rcx, BERP_IE_Context
  ... truncated ...
```
