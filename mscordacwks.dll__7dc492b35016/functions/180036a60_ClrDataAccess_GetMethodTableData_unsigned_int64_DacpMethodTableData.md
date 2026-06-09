# ClrDataAccess::GetMethodTableData(unsigned __int64,DacpMethodTableData *)

- ea: `0x180036a60`
- end: `0x180036e55`
- name: `?GetMethodTableData@ClrDataAccess@@UEAAJ_KPEAUDacpMethodTableData@@@Z`
- size: `1013`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, struct DacpMethodTableData *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x1800328f0`
- `0x180036a60`
- `0x180041044`
- `0x18007d5c8`
- `0x180081de0`
- `0x180082278`
- `0x180082c58`
- `0x1800f3020`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180036a9a`
- `KERNEL32!EnterCriticalSection` at `0x180036a9a`
- `KERNEL32!LeaveCriticalSection` at `0x180036e31`
- `KERNEL32!LeaveCriticalSection` at `0x180036e31`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ClrDataAccess::GetMethodTableData(
        ClrDataAccess *this,
        unsigned __int64 a2,
        struct DacpMethodTableData *a3)
{
  unsigned int v6; // ebx
  ClrDataAccess *v7; // r15
  unsigned __int64 *v8; // rdi
  int v9; // ecx
  int v11; // eax
  int v12; // eax
  unsigned __int64 *Module; // rax
  __int64 *v14; // rax
  __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  void *v20; // rax
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  void *v23; // rax
  unsigned __int64 v24; // rcx
  BOOL v25; // eax
  struct Exception *v27; // rbx
  BOOL v28; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v30; // rcx
  ClrDataAccess *v31; // [rsp+20h] [rbp-78h]
  struct Exception *v32; // [rsp+28h] [rbp-70h] BYREF
  BOOL v33; // [rsp+30h] [rbp-68h]
  struct Exception *v34; // [rsp+38h] [rbp-60h] BYREF
  struct Exception *v35; // [rsp+48h] [rbp-50h]
  _QWORD v36[9]; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v38; // [rsp+A8h] [rbp+10h] BYREF
  unsigned __int64 v39; // [rsp+B8h] [rbp+20h] BYREF

  v6 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v7 = g_dacImpl;
  v31 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v38 = 0;
  v35 = 0;
  try
  {
    try
    {
      v39 = a2;
      v8 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(a2, 0x40u, 1, 1);
      LODWORD(v39) = 0;
      if ( !(unsigned int)DacValidateMethodTable((struct MethodTable *)v8, (int *)&v39) )
      {
        v6 = -2147024809;
        v38 = -2147024809;
        goto LABEL_57;
      }
      memset(a3, 0, 0x48u);
      v9 = *((_DWORD *)v8 + 1);
      *((_DWORD *)a3 + 10) = v9;
      if ( *(int *)v8 < 0 && (*(_DWORD *)v8 & 0xC0000) != 0x80000 )
        *((_DWORD *)a3 + 10) = v9 - 2;
      if ( *(int *)v8 >= 0 )
        v11 = 0;
      else
        v11 = *(unsigned __int16 *)v8;
      *((_DWORD *)a3 + 11) = v11;
      v12 = v39;
      *(_DWORD *)a3 = v39;
      if ( v12 )
        goto LABEL_57;
      Module = (unsigned __int64 *)MethodTable::GetModule(v8, &v32);
      v14 = DacInstantiateClassByVTable(*Module, 1576, 1);
      LOBYTE(v15) = 1;
      *((_QWORD *)a3 + 1) = DacGetTargetAddrForHostAddr(v14, v15);
      v16 = v8[5];
      if ( (v16 & 2) != 0 )
      {
        if ( (v16 & 1) == 0 )
        {
          v39 = v16 - 2;
          v16 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v16 - 2, 0x40u, 1, 1) + 5);
          v39 = v16;
LABEL_21:
          v17 = DacInstantiateTypeByAddressHelper(v16, 0x48u, 1, 1);
          LOBYTE(v18) = 1;
          *((_QWORD *)a3 + 2) = DacGetTargetAddrForHostAddr(v17, v18);
          v19 = v8[2];
          if ( (*(_DWORD *)v8 & 0x800000) != 0 )
          {
            v39 = v19 + 16;
            v19 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v19 + 16, 8u, 1, 1);
          }
          v39 = v19;
          v20 = DacInstantiateTypeByAddressHelper(v19, 0x40u, 1, 1);
          LOBYTE(v21) = 1;
          *((_QWORD *)a3 + 3) = DacGetTargetAddrForHostAddr(v20, v21);
          *((_WORD *)a3 + 16) = *((_WORD *)v8 + 7);
          v22 = v8[5];
          if ( (v22 & 2) != 0 )
          {
            if ( (v22 & 1) == 0 )
            {
              v39 = v22 - 2;
              v22 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v22 - 2, 0x40u, 1, 1) + 5);
              v39 = v22;
LABEL_28:
              v23 = DacInstantiateTypeByAddressHelper(v22, 0x48u, 1, 1);
              *((_WORD *)a3 + 17) = EEClass::GetPackableField(v23, 1);
              *((_WORD *)a3 + 18) = MethodTable::GetNumVtableSlots((MethodTable *)v8);
              *((_WORD *)a3 + 19) = *((_WORD *)v8 + 6);
              *((_DWORD *)a3 + 12) = MethodTable::GetTypeDefRid_NoLogging((MethodTable *)v8) | 0x2000000;
              v24 = v8[5];
              if ( (v24 & 2) != 0 )
              {
                if ( (v24 & 1) == 0 )
                {
                  v39 = v24 - 2;
                  v24 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v24 - 2, 0x40u, 1, 1) + 5);
                  v39 = v24;
                  goto LABEL_33;
                }
                v39 = v24 - 3;
                v39 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v24 - 3, 8u, 1, 1);
                v24 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v39, 0x40u, 1, 1) + 5);
              }
              v39 = v24;
LABEL_33:
              *((_DWORD *)a3 + 13) = *((_DWORD *)DacInstantiateTypeByAddressHelper(v24, 0x48u, 1, 1) + 14);
              *((_DWORD *)a3 + 16) = *(_DWORD *)v8 & 0x1000000;
              *((_DWORD *)a3 + 14) = MethodTable::IsDomainNeutral((MethodTable *)v8) != 0;
              v25 = *(int *)v8 >= 0 && (*(_BYTE *)v8 & 6) != 0;
              *((_DWORD *)a3 + 15) = v25;
              goto LABEL_57;
            }
            v39 = v22 - 3;
            v39 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v22 - 3, 8u, 1, 1);
            v22 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v39, 0x40u, 1, 1) + 5);
          }
          v39 = v22;
          goto LABEL_28;
        }
        v39 = v16 - 3;
        v39 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v16 - 3, 8u, 1, 1);
        v16 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v39, 0x40u, 1, 1) + 5);
      }
      v39 = v16;
      goto LABEL_21;
    }
    catch ( Exception *v34 )
    {
      v35 = v34;
      throw;
    }
  }
  catch ( ... )
  {
    v36[1] = 0;
    v36[0] = &DelegatingException::`vftable';
    v36[2] = -1;
    v27 = v35;
    v32 = v35;
    v28 = v35 != 0;
    v33 = v28;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v30 = (struct Exception *)v36;
    if ( v27 )
      v30 = v27;
    if ( !DacExceptionFilter(v30, (ClrDataAccess *)((char *)this - 16), (int *)&v38) )
    {
      v33 = 0;
      throw;
    }
    if ( v28 )
    {
      if ( v27 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v27 + 80LL))(v27) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v27)(v27, 5);
      }
      v33 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v36);
    v7 = v31;
    v6 = v38;
  }
LABEL_57:
  g_dacImpl = v7;
  LeaveCriticalSection(&g_dacCritSec);
  return v6;
}

```

## disassembly

```asm
0x180036a60  mov     [rsp+arg_10], rbx
0x180036a65  mov     [rsp+arg_0], rcx
0x180036a6a  push    rsi
0x180036a6b  push    rdi
0x180036a6c  push    r13
0x180036a6e  push    r14
0x180036a70  push    r15
0x180036a72  sub     rsp, 70h
0x180036a76  mov     r14, r8
0x180036a79  mov     rdi, rdx
0x180036a7c  mov     rsi, rcx
0x180036a7f  xor     ebx, ebx
0x180036a81  test    rdx, rdx
0x180036a84  jz      loc_180036E3B
0x180036a8a  test    r8, r8
0x180036a8d  jz      loc_180036E3B
0x180036a93  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036a9a  call    cs:__imp_EnterCriticalSection
0x180036aa0  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180036aa7  mov     [rsp+98h+var_78], r15
0x180036aac  lea     rax, [rsi-10h]
0x180036ab0  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180036ab7  mov     [rsp+98h+arg_8], ebx
0x180036abe  mov     [rsp+98h+var_50], rbx
0x180036ac3  lea     rax, [rsp+98h+var_58]
0x180036ac8  mov     [rsp+98h+arg_18], rax
0x180036ad0  mov     [rsp+98h+arg_18], rdi
0x180036ad8  lea     esi, [rbx+1]
0x180036adb  mov     r9b, sil; bool
0x180036ade  mov     r8b, sil; bool
0x180036ae1  lea     r13d, [rbx+40h]
0x180036ae5  mov     edx, r13d; unsigned int
0x180036ae8  mov     rcx, rdi; unsigned __int64
0x180036aeb  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036af0  mov     rdi, rax
0x180036af3  mov     dword ptr [rsp+98h+arg_18], ebx
0x180036afa  lea     rdx, [rsp+98h+arg_18]; int *
0x180036b02  mov     rcx, rax; struct MethodTable *
0x180036b05  call    ?DacValidateMethodTable@@YAHPEAVMethodTable@@AEAH@Z; DacValidateMethodTable(MethodTable *,int &)
0x180036b0a  test    eax, eax
0x180036b0c  jnz     short loc_180036B1F
0x180036b0e  mov     ebx, 80070057h
0x180036b13  mov     [rsp+98h+arg_8], ebx
0x180036b1a  jmp     loc_180036E15
0x180036b1f  xor     edx, edx; Val
0x180036b21  lea     r8d, [rdx+48h]; Size
0x180036b25  mov     rcx, r14; void *
0x180036b28  call    memset
0x180036b2d  mov     ecx, [rdi+4]
0x180036b30  mov     [r14+28h], ecx
0x180036b34  mov     eax, [rdi]
0x180036b36  test    eax, eax
0x180036b38  jns     short loc_180036B4A
0x180036b3a  and     eax, 0C0000h
0x180036b3f  cmp     eax, 80000h
0x180036b44  jz      short loc_180036B4A
0x180036b46  mov     eax, esi
0x180036b48  jmp     short loc_180036B4C
0x180036b4a  mov     eax, ebx
0x180036b4c  test    eax, eax
0x180036b4e  jz      short loc_180036B57
0x180036b50  lea     eax, [rcx-2]
0x180036b53  mov     [r14+28h], eax
0x180036b57  cmp     [rdi], ebx
0x180036b59  jge     short loc_180036B60
0x180036b5b  movzx   eax, word ptr [rdi]
0x180036b5e  jmp     short loc_180036B62
0x180036b60  mov     eax, ebx
0x180036b62  mov     [r14+2Ch], eax
0x180036b66  mov     eax, dword ptr [rsp+98h+arg_18]
0x180036b6d  mov     [r14], eax
0x180036b70  test    eax, eax
0x180036b72  jnz     loc_180036E15
0x180036b78  lea     rdx, [rsp+98h+var_70]
0x180036b7d  mov     rcx, rdi
0x180036b80  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x180036b85  mov     r8b, sil
0x180036b88  mov     edx, 628h
0x180036b8d  mov     rcx, [rax]; unsigned __int64
0x180036b90  call    DacInstantiateClassByVTable
0x180036b95  mov     dl, sil
0x180036b98  mov     rcx, rax
0x180036b9b  call    DacGetTargetAddrForHostAddr
0x180036ba0  mov     [r14+8], rax
0x180036ba4  mov     rcx, [rdi+28h]
0x180036ba8  test    cl, 2
0x180036bab  jnz     short loc_180036BB7
0x180036bad  mov     [rsp+98h+arg_18], rcx
0x180036bb5  jmp     short loc_180036C1D
0x180036bb7  test    sil, cl
0x180036bba  jz      short loc_180036BF7
0x180036bbc  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x180036bc0  mov     [rsp+98h+arg_18], rcx
0x180036bc8  mov     r9b, sil; bool
0x180036bcb  mov     r8b, sil; bool
0x180036bce  mov     edx, 8; unsigned int
0x180036bd3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036bd8  mov     rcx, [rax]; unsigned __int64
0x180036bdb  mov     [rsp+98h+arg_18], rcx
0x180036be3  mov     r9b, sil; bool
0x180036be6  mov     r8b, sil; bool
0x180036be9  mov     edx, r13d; unsigned int
0x180036bec  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036bf1  mov     rcx, [rax+28h]
0x180036bf5  jmp     short loc_180036BAD
0x180036bf7  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180036bfb  mov     [rsp+98h+arg_18], rcx
0x180036c03  mov     r9b, sil; bool
0x180036c06  mov     r8b, sil; bool
0x180036c09  mov     edx, r13d; unsigned int
0x180036c0c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036c11  mov     rcx, [rax+28h]; unsigned __int64
0x180036c15  mov     [rsp+98h+arg_18], rcx
0x180036c1d  mov     r9b, sil; bool
0x180036c20  mov     r8b, sil; bool
0x180036c23  mov     edx, 48h ; 'H'; unsigned int
0x180036c28  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036c2d  mov     dl, sil
0x180036c30  mov     rcx, rax
0x180036c33  call    DacGetTargetAddrForHostAddr
0x180036c38  mov     [r14+10h], rax
0x180036c3c  mov     rcx, [rdi+10h]
0x180036c40  test    dword ptr [rdi], 800000h
0x180036c46  jz      short loc_180036C67
0x180036c48  add     rcx, 10h; unsigned __int64
0x180036c4c  mov     [rsp+98h+arg_18], rcx
0x180036c54  mov     r9b, sil; bool
0x180036c57  mov     r8b, sil; bool
0x180036c5a  mov     edx, 8; unsigned int
0x180036c5f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036c64  mov     rcx, [rax]; unsigned __int64
0x180036c67  mov     [rsp+98h+arg_18], rcx
0x180036c6f  mov     r9b, sil; bool
0x180036c72  mov     r8b, sil; bool
0x180036c75  mov     edx, r13d; unsigned int
0x180036c78  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036c7d  mov     dl, sil
0x180036c80  mov     rcx, rax
0x180036c83  call    DacGetTargetAddrForHostAddr
0x180036c88  mov     [r14+18h], rax
0x180036c8c  movzx   eax, word ptr [rdi+0Eh]
0x180036c90  mov     [r14+20h], ax
0x180036c95  mov     rcx, [rdi+28h]
0x180036c99  test    cl, 2
0x180036c9c  jnz     short loc_180036CA8
0x180036c9e  mov     [rsp+98h+arg_18], rcx
0x180036ca6  jmp     short loc_180036D0E
0x180036ca8  test    sil, cl
0x180036cab  jz      short loc_180036CE8
0x180036cad  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x180036cb1  mov     [rsp+98h+arg_18], rcx
0x180036cb9  mov     r9b, sil; bool
0x180036cbc  mov     r8b, sil; bool
0x180036cbf  mov     edx, 8; unsigned int
0x180036cc4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036cc9  mov     rcx, [rax]; unsigned __int64
0x180036ccc  mov     [rsp+98h+arg_18], rcx
0x180036cd4  mov     r9b, sil; bool
0x180036cd7  mov     r8b, sil; bool
0x180036cda  mov     edx, r13d; unsigned int
0x180036cdd  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036ce2  mov     rcx, [rax+28h]
0x180036ce6  jmp     short loc_180036C9E
0x180036ce8  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180036cec  mov     [rsp+98h+arg_18], rcx
0x180036cf4  mov     r9b, sil; bool
0x180036cf7  mov     r8b, sil; bool
0x180036cfa  mov     edx, r13d; unsigned int
0x180036cfd  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036d02  mov     rcx, [rax+28h]; unsigned __int64
0x180036d06  mov     [rsp+98h+arg_18], rcx
0x180036d0e  mov     r9b, sil; bool
0x180036d11  mov     r8b, sil; bool
0x180036d14  mov     edx, 48h ; 'H'; unsigned int
0x180036d19  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036d1e  mov     edx, esi
0x180036d20  mov     rcx, rax
0x180036d23  call    ?GetPackableField@EEClass@@AEAAKW4EEClassFieldId@@@Z; EEClass::GetPackableField(EEClassFieldId)
0x180036d28  mov     [r14+22h], ax
0x180036d2d  mov     rcx, rdi; this
0x180036d30  call    ?GetNumVtableSlots@MethodTable@@QEAAGXZ; MethodTable::GetNumVtableSlots(void)
0x180036d35  mov     [r14+24h], ax
0x180036d3a  movzx   eax, word ptr [rdi+0Ch]
0x180036d3e  mov     [r14+26h], ax
0x180036d43  mov     rcx, rdi; this
0x180036d46  call    ?GetTypeDefRid_NoLogging@MethodTable@@QEAAIXZ; MethodTable::GetTypeDefRid_NoLogging(void)
0x180036d4b  bts     eax, 19h
0x180036d4f  mov     [r14+30h], eax
0x180036d53  mov     rcx, [rdi+28h]
0x180036d57  test    cl, 2
0x180036d5a  jnz     short loc_180036D66
0x180036d5c  mov     [rsp+98h+arg_18], rcx
0x180036d64  jmp     short loc_180036DCC
0x180036d66  test    sil, cl
0x180036d69  jz      short loc_180036DA6
0x180036d6b  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x180036d6f  mov     [rsp+98h+arg_18], rcx
0x180036d77  mov     r9b, sil; bool
0x180036d7a  mov     r8b, sil; bool
0x180036d7d  mov     edx, 8; unsigned int
0x180036d82  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036d87  mov     rcx, [rax]; unsigned __int64
0x180036d8a  mov     [rsp+98h+arg_18], rcx
0x180036d92  mov     r9b, sil; bool
0x180036d95  mov     r8b, sil; bool
0x180036d98  mov     edx, r13d; unsigned int
0x180036d9b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036da0  mov     rcx, [rax+28h]
0x180036da4  jmp     short loc_180036D5C
0x180036da6  add     rcx, 0FFFFFFFFFFFFFFFEh; unsigned __int64
0x180036daa  mov     [rsp+98h+arg_18], rcx
0x180036db2  mov     r9b, sil; bool
0x180036db5  mov     r8b, sil; bool
0x180036db8  mov     edx, r13d; unsigned int
0x180036dbb  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036dc0  mov     rcx, [rax+28h]; unsigned __int64
0x180036dc4  mov     [rsp+98h+arg_18], rcx
0x180036dcc  mov     r9b, sil; bool
0x180036dcf  mov     r8b, sil; bool
0x180036dd2  mov     edx, 48h ; 'H'; unsigned int
0x180036dd7  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180036ddc  mov     eax, [rax+38h]
0x180036ddf  mov     [r14+34h], eax
0x180036de3  mov     eax, [rdi]
0x180036de5  and     eax, 1000000h
0x180036dea  mov     [r14+40h], eax
0x180036dee  mov     rcx, rdi; this
0x180036df1  call    ?IsDomainNeutral@MethodTable@@QEAAHXZ; MethodTable::IsDomainNeutral(void)
0x180036df6  mov     ecx, ebx
0x180036df8  test    eax, eax
0x180036dfa  setnz   cl
0x180036dfd  mov     [r14+38h], ecx
0x180036e01  cmp     [rdi], ebx
0x180036e03  jge     short loc_180036E09
0x180036e05  mov     eax, ebx
0x180036e07  jmp     short loc_180036E11
0x180036e09  test    byte ptr [rdi], 6
0x180036e0c  mov     eax, ebx
0x180036e0e  setnz   al
0x180036e11  mov     [r14+3Ch], eax
0x180036e15  jmp     short loc_180036E23
0x180036e17  mov     r15, [rsp+98h+var_78]
0x180036e1c  mov     ebx, [rsp+98h+arg_8]
0x180036e23  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r15; ClrDataAccess * g_dacImpl
0x180036e2a  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036e31  call    cs:__imp_LeaveCriticalSection
0x180036e37  mov     eax, ebx
0x180036e39  jmp     short loc_180036E40
0x180036e3b  mov     eax, 80070057h
0x180036e40  mov     rbx, [rsp+98h+arg_10]
0x180036e48  add     rsp, 70h
0x180036e4c  pop     r15
0x180036e4e  pop     r14
0x180036e50  pop     r13
0x180036e52  pop     rdi
0x180036e53  pop     rsi
0x180036e54  retn
```
