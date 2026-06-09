# XMLHttp::setErrorInfo(long,ulong)

- ea: `0x18004aef4`
- end: `0x18004b0f8`
- name: `?setErrorInfo@XMLHttp@@IEAAXJK@Z`
- size: `516`
- prototype: `void(XMLHttp *__hidden this, int, unsigned int)`
- caller_count: `19`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800dcae0`
- `0x1800dcc20`
- `0x1800dcd60`
- `0x1800dcf00`
- `0x1800dd060`
- `0x1800dd1a0`
- `0x1800dd2e0`
- `0x1800dd420`
- `0x1800dd580`
- `0x1800dd6c0`
- `0x1800ddca0`
- `0x1800dde60`
- `0x1800ddfa0`
- `0x1800de110`
- `0x1800de270`
- `0x1800de3f0`
- `0x1800de530`
- `0x1800de670`
- `0x1800de7c0`

## callees

- `0x18001b690`
- `0x1800384a8`
- `0x180046640`
- `0x18004a8fc`
- `0x18004ab2c`
- `0x18004abb8`
- `0x18004aef4`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18004afc9`
- `msvcrt!_resetstkoflw` at `0x18004afc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b01c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004b01c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004afb7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004afb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b054`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b054`
- `OLEAUT32!__imp_SysStringLen` at `0x18004af92`
- `OLEAUT32!__imp_SysStringLen` at `0x18004af92`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18004af59`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18004af59`

## pseudocode

```c
void __fastcall XMLHttp::setErrorInfo(XMLHttp *this, int a2, DWORD a3)
{
  signed int v3; // edi
  bool v5; // cl
  struct String *v6; // rdi
  UINT v7; // eax
  struct Exception *v8; // rax
  struct String *v9; // rax
  struct Exception *v10; // rax
  IErrorInfo *pperrinfo[3]; // [rsp+30h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 < 0 )
  {
    v3 = a3;
    if ( *((_BYTE *)this + 136) )
    {
      pperrinfo[0] = 0;
      v5 = 0;
      if ( (a2 & 0x1FFF0000) == 0x70000 )
        v5 = (unsigned int)(unsigned __int16)a2 - 12001 <= 0xC0;
      if ( !v5 || GetErrorInfo(0, pperrinfo) )
      {
        v6 = Resources::formatMessage(a2, 0, 0, 0, 0);
      }
      else
      {
        v6 = 0;
        pbstr = 0;
        if ( !((unsigned int (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo[0]->lpVtbl->GetDescription)(
                pperrinfo[0],
                &pbstr) )
        {
          v7 = SysStringLen(pbstr);
          v6 = ArrayString::newString(pbstr, v7);
          pperrinfo[1] = (IErrorInfo *)v6;
          SysFreeString(pbstr);
        }
      }
      if ( pperrinfo[0] )
      {
        ((void (__fastcall *)(IErrorInfo *))pperrinfo[0]->lpVtbl->Release)(pperrinfo[0]);
        pperrinfo[0] = 0;
      }
      if ( v6 )
      {
        v8 = Exception::newException(a2, a2, v6);
        Exception::raiseException(v8);
        __debugbreak();
      }
      Exception::throwHR(a2);
    }
    if ( a3 )
    {
      v9 = Resources::FormatSystemMessage(a3);
      if ( v9 )
      {
        if ( v3 > 0 )
          v3 = (unsigned __int16)v3 | 0x80070000;
        v10 = Exception::newException(v3, v3, v9);
        Exception::raiseException(v10);
        __debugbreak();
      }
      Exception::throwHR(a2);
    }
  }
}

```

## disassembly

```asm
0x18004aef4  test    edx, edx
0x18004aef6  jns     locret_18004B0F7
0x18004aefc  mov     rax, rsp
0x18004aeff  mov     [rax+8], rbx
0x18004af03  mov     [rax+18h], rsi
0x18004af07  mov     [rax+10h], edx
0x18004af0a  push    rdi
0x18004af0b  sub     rsp, 40h
0x18004af0f  mov     edi, r8d
0x18004af12  mov     esi, edx
0x18004af14  xor     ebx, ebx
0x18004af16  cmp     [rcx+88h], bl
0x18004af1c  jz      loc_18004B0AE
0x18004af22  mov     [rax-18h], rbx
0x18004af26  movzx   ecx, bl
0x18004af29  mov     eax, edx
0x18004af2b  and     eax, 1FFF0000h
0x18004af30  cmp     eax, 70000h
0x18004af35  jnz     short loc_18004AF4A
0x18004af37  movzx   eax, si
0x18004af3a  sub     eax, 2EE1h
0x18004af3f  lea     edx, [rbx+1]
0x18004af42  cmp     eax, 0C0h
0x18004af47  cmovbe  ecx, edx
0x18004af4a  test    cl, cl
0x18004af4c  jz      loc_18004B05C
0x18004af52  lea     rdx, [rsp+48h+pperrinfo]; pperrinfo
0x18004af57  xor     ecx, ecx; dwReserved
0x18004af59  call    cs:__imp_GetErrorInfo
0x18004af5f  test    eax, eax
0x18004af61  jnz     loc_18004B05C
0x18004af67  mov     rdi, rbx
0x18004af6a  mov     [rsp+48h+pbstr], rbx
0x18004af6f  mov     rcx, [rsp+48h+pperrinfo]
0x18004af74  mov     rax, [rcx]
0x18004af77  lea     rdx, [rsp+48h+pbstr]
0x18004af7c  mov     rax, [rax+28h]
0x18004af80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af85  test    eax, eax
0x18004af87  jnz     loc_18004B073
0x18004af8d  mov     rcx, [rsp+48h+pbstr]; pbstr
0x18004af92  call    cs:__imp_SysStringLen
0x18004af98  mov     edx, eax; int
0x18004af9a  mov     rcx, [rsp+48h+pbstr]; Src
0x18004af9f  call    ?newString@ArrayString@@SAPEAV1@PEBGH@Z; ArrayString::newString(ushort const *,int)
0x18004afa4  mov     rdi, rax
0x18004afa7  mov     [rsp+48h+var_10], rax
0x18004afac  jmp     loc_18004B04F
0x18004afb1  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18004afb7  call    cs:__imp_TlsGetValue
0x18004afbd  mov     rbx, rax
0x18004afc0  cmp     dword ptr [rax+54h], 0C00000FDh
0x18004afc7  jnz     short loc_18004B042
0x18004afc9  call    cs:__imp__resetstkoflw
0x18004afcf  test    eax, eax
0x18004afd1  jnz     short loc_18004B024
0x18004afd3  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18004afda  test    rcx, rcx
0x18004afdd  jz      short loc_18004AFF1
0x18004afdf  cmp     [rcx+50h], rbx
0x18004afe3  jnz     short loc_18004AFF1
0x18004afe5  mov     rax, [rcx]
0x18004afe8  mov     rax, [rax+20h]
0x18004afec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aff1  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18004aff8  test    rcx, rcx
0x18004affb  jz      short loc_18004B00F
0x18004affd  cmp     [rcx+50h], rbx
0x18004b001  jnz     short loc_18004B00F
0x18004b003  mov     rax, [rcx]
0x18004b006  mov     rax, [rax+20h]
0x18004b00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b00f  xor     r9d, r9d; lpArguments
0x18004b012  xor     r8d, r8d; nNumberOfArguments
0x18004b015  xor     edx, edx; dwExceptionFlags
0x18004b017  mov     ecx, 0C00000FDh; dwExceptionCode
0x18004b01c  call    cs:__imp_RaiseException
0x18004b022  jmp     short loc_18004B042
0x18004b024  mov     rax, [rbx+60h]
0x18004b028  mov     [rbx+68h], rax
0x18004b02c  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18004b033  mov     [rbx+60h], rax
0x18004b037  mov     dword ptr [rbx+54h], 800703E9h
0x18004b03e  mov     byte ptr [rbx+78h], 0
0x18004b042  xor     edi, edi
0x18004b044  mov     [rsp+48h+var_10], rdi
0x18004b049  xor     ebx, ebx
0x18004b04b  mov     esi, [rsp+48h+arg_8]
0x18004b04f  mov     rcx, [rsp+48h+pbstr]; bstrString
0x18004b054  call    cs:__imp_SysFreeString
0x18004b05a  jmp     short loc_18004B073
0x18004b05c  mov     [rsp+48h+var_28], rbx; struct String *
0x18004b061  xor     r9d, r9d; struct String *
0x18004b064  xor     r8d, r8d; struct String *
0x18004b067  xor     edx, edx; struct String *
0x18004b069  mov     ecx, esi; int
0x18004b06b  call    ?formatMessage@Resources@@SAPEAVString@@JPEAV2@000@Z; Resources::formatMessage(long,String *,String *,String *,String *)
0x18004b070  mov     rdi, rax
0x18004b073  mov     rcx, [rsp+48h+pperrinfo]
0x18004b078  test    rcx, rcx
0x18004b07b  jz      short loc_18004B08E
0x18004b07d  mov     rax, [rcx]
0x18004b080  mov     rax, [rax+10h]
0x18004b084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b089  mov     [rsp+48h+pperrinfo], rbx
0x18004b08e  mov     ecx, esi; int
0x18004b090  test    rdi, rdi
0x18004b093  jz      short loc_18004B0A8
0x18004b095  mov     r8, rdi; struct String *
0x18004b098  mov     edx, esi; int
0x18004b09a  call    ?newException@Exception@@SAPEAV1@JJPEAVString@@@Z; Exception::newException(long,long,String *)
0x18004b09f  mov     rcx, rax; struct Exception *
0x18004b0a2  call    ?raiseException@Exception@@KAXPEAV1@@Z; Exception::raiseException(Exception *)
0x18004b0a7  int     3; Trap to Debugger
0x18004b0a8  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18004b0ae  test    edi, edi
0x18004b0b0  jz      short loc_18004B0E8
0x18004b0b2  mov     ecx, edi; dwMessageId
0x18004b0b4  call    ?FormatSystemMessage@Resources@@SAPEAVString@@J@Z; Resources::FormatSystemMessage(long)
0x18004b0b9  test    rax, rax
0x18004b0bc  jz      short loc_18004B0E0
0x18004b0be  test    edi, edi
0x18004b0c0  jle     short loc_18004B0CB
0x18004b0c2  movzx   edi, di
0x18004b0c5  or      edi, 80070000h
0x18004b0cb  mov     r8, rax; struct String *
0x18004b0ce  mov     edx, edi; int
0x18004b0d0  mov     ecx, edi; int
0x18004b0d2  call    ?newException@Exception@@SAPEAV1@JJPEAVString@@@Z; Exception::newException(long,long,String *)
0x18004b0d7  mov     rcx, rax; struct Exception *
0x18004b0da  call    ?raiseException@Exception@@KAXPEAV1@@Z; Exception::raiseException(Exception *)
0x18004b0df  int     3; Trap to Debugger
0x18004b0e0  mov     ecx, esi; int
0x18004b0e2  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18004b0e8  mov     rbx, [rsp+48h+arg_0]
0x18004b0ed  mov     rsi, [rsp+48h+arg_10]
0x18004b0f2  add     rsp, 40h
0x18004b0f6  pop     rdi
0x18004b0f7  retn
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
