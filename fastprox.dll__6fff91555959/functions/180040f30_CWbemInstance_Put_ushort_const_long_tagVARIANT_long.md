# CWbemInstance::Put(ushort const *,long,tagVARIANT *,long)

- ea: `0x180040f30`
- end: `0x180041211`
- name: `?Put@CWbemInstance@@UEAAJPEBGJPEAUtagVARIANT@@J@Z`
- size: `737`
- prototype: `__int64 __fastcall(CWbemInstance *this, const unsigned __int16 *, int, struct tagVARIANT *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180040f30`
- `0x180050490`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004106e`
- `wbemcomn!GetMemLogObject` at `0x1800410f1`
- `wbemcomn!GetMemLogObject` at `0x18004115f`
- `wbemcomn!GetMemLogObject` at `0x1800411f1`
- `wbemcomn!GetMemLogObject` at `0x18004106e`
- `wbemcomn!GetMemLogObject` at `0x1800410f1`
- `wbemcomn!GetMemLogObject` at `0x18004115f`
- `wbemcomn!GetMemLogObject` at `0x1800411f1`
- `wbemcomn!?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z` at `0x180040f95`
- `wbemcomn!?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z` at `0x180040f95`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x180041063`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x180041063`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180040f77`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180040f77`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004107c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800410ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004116d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800411fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004107c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800410ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004116d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800411fc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180041015`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180041041`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004109a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180041015`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180041041`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004109a`

## pseudocode

```c
__int64 __fastcall CWbemInstance::Put(
        CWbemInstance *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4,
        unsigned int a5)
{
  int v9; // edi
  __int64 result; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CWbemInstance *v16; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v17[80]; // [rsp+38h] [rbp-50h] BYREF

  try
  {
    v16 = this;
    (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 280LL))(this, 0);
    if ( a2 )
    {
      if ( (a3 & 0xFFFDFFFF) != 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217400);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749896LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v16);
        result = 2147749896LL;
      }
      else
      {
        CVar::CVar((CVar *)v17);
        if ( !a4 )
        {
          CVar::SetAsNull((CVar *)v17);
LABEL_6:
          v9 = (*(__int64 (__fastcall **)(CWbemInstance *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
                 this,
                 a2,
                 v17,
                 a5);
          if ( (*(int (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 744LL))(this, 0) < 0 )
          {
            v9 = -2147217407;
          }
          else
          {
            if ( v9 == -2147217406 )
            {
              CVar::~CVar((CVar *)v17);
              (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
              return 2147749890LL;
            }
            if ( v9 >= 0 )
              goto LABEL_9;
          }
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, v9);
LABEL_9:
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              (unsigned int)v9);
          }
          CVar::~CVar((CVar *)v17);
          (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          return (unsigned int)v9;
        }
        if ( !CVar::SetVariant((CVar *)v17, a4, 1) )
          goto LABEL_6;
        v11 = GetMemLogObject();
        CMemoryLog::Write(v11, -2147217403);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749893LL);
        }
        CVar::~CVar((CVar *)v17);
        (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        result = 2147749893LL;
      }
    }
    else
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v16 = this;
}

```

## disassembly

```asm
0x180040f30  push    rbx
0x180040f32  push    rsi
0x180040f33  push    rdi
0x180040f34  push    r14
0x180040f36  sub     rsp, 68h
0x180040f3a  mov     rdi, r9
0x180040f3d  mov     esi, r8d
0x180040f40  mov     r14, rdx
0x180040f43  mov     rbx, rcx
0x180040f46  mov     [rsp+88h+var_58], rcx
0x180040f4b  mov     rax, [rcx]
0x180040f4e  xor     edx, edx
0x180040f50  mov     rax, [rax+118h]
0x180040f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f5c  nop
0x180040f5d  test    r14, r14
0x180040f60  jz      loc_1800410F1
0x180040f66  test    esi, 0FFFDFFFFh
0x180040f6c  jnz     loc_18004115F
0x180040f72  lea     rcx, [rsp+88h+var_50]
0x180040f77  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180040f7d  nop
0x180040f7e  lea     rcx, [rsp+88h+var_50]
0x180040f83  test    rdi, rdi
0x180040f86  jz      loc_180041063
0x180040f8c  mov     r8d, 1
0x180040f92  mov     rdx, rdi
0x180040f95  call    cs:__imp_?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z; CVar::SetVariant(tagVARIANT *,int)
0x180040f9b  test    eax, eax
0x180040f9d  jnz     loc_18004106E
0x180040fa3  mov     rax, [rbx]
0x180040fa6  mov     r9d, [rsp+88h+arg_20]
0x180040fae  lea     r8, [rsp+88h+var_50]
0x180040fb3  mov     rdx, r14
0x180040fb6  mov     rcx, rbx
0x180040fb9  mov     rax, [rax+368h]
0x180040fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fc5  mov     edi, eax
0x180040fc7  mov     rax, [rbx]
0x180040fca  xor     edx, edx
0x180040fcc  mov     rcx, rbx
0x180040fcf  mov     rax, [rax+2E8h]
0x180040fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fdb  test    eax, eax
0x180040fdd  js      loc_1800411EC
0x180040fe3  cmp     edi, 80041002h
0x180040fe9  jz      short loc_18004103C
0x180040feb  test    edi, edi
0x180040fed  js      loc_1800411F1
0x180040ff3  lea     rax, WPP_GLOBAL_Control
0x180040ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180041001  cmp     rcx, rax
0x180041004  jz      short loc_180041010
0x180041006  test    byte ptr [rcx+1Ch], 1
0x18004100a  jnz     loc_1800410BF
0x180041010  lea     rcx, [rsp+88h+var_50]
0x180041015  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004101b  nop
0x18004101c  mov     rcx, [rbx]
0x18004101f  mov     rax, [rcx+120h]
0x180041026  xor     edx, edx
0x180041028  mov     rcx, rbx
0x18004102b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041030  mov     eax, edi
0x180041032  add     rsp, 68h
0x180041036  pop     r14
0x180041038  pop     rdi
0x180041039  pop     rsi
0x18004103a  pop     rbx
0x18004103b  retn
0x18004103c  lea     rcx, [rsp+88h+var_50]
0x180041041  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180041047  nop
0x180041048  mov     rcx, [rbx]
0x18004104b  mov     rax, [rcx+120h]
0x180041052  xor     edx, edx
0x180041054  mov     rcx, rbx
0x180041057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004105c  mov     eax, 80041002h
0x180041061  jmp     short loc_180041032
0x180041063  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x180041069  jmp     loc_180040FA3
0x18004106e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041074  mov     edx, 80041005h
0x180041079  mov     rcx, rax
0x18004107c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041082  lea     rax, WPP_GLOBAL_Control
0x180041089  mov     rcx, cs:WPP_GLOBAL_Control
0x180041090  cmp     rcx, rax
0x180041093  jnz     short loc_1800410E6
0x180041095  lea     rcx, [rsp+88h+var_50]
0x18004109a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800410a0  nop
0x1800410a1  mov     rcx, [rbx]
0x1800410a4  mov     rax, [rcx+120h]
0x1800410ab  xor     edx, edx
0x1800410ad  mov     rcx, rbx
0x1800410b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410b5  mov     eax, 80041005h
0x1800410ba  jmp     loc_180041032
0x1800410bf  cmp     byte ptr [rcx+19h], 2
0x1800410c3  jb      loc_180041010
0x1800410c9  mov     edx, 23h ; '#'
0x1800410ce  mov     r9d, edi
0x1800410d1  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x1800410d8  mov     rcx, [rcx+10h]
0x1800410dc  call    WPP_SF_d
0x1800410e1  jmp     loc_180041010
0x1800410e6  test    byte ptr [rcx+1Ch], 1
0x1800410ea  jz      short loc_180041095
0x1800410ec  jmp     loc_1800411C2
0x1800410f1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800410f7  mov     edx, 80041008h
0x1800410fc  mov     rcx, rax
0x1800410ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041105  lea     rax, WPP_GLOBAL_Control
0x18004110c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041113  cmp     rcx, rax
0x180041116  jnz     short loc_180041136
0x180041118  mov     rcx, [rbx]
0x18004111b  mov     rax, [rcx+120h]
0x180041122  xor     edx, edx
0x180041124  mov     rcx, rbx
0x180041127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004112c  mov     eax, 80041008h
0x180041131  jmp     loc_180041032
0x180041136  test    byte ptr [rcx+1Ch], 1
0x18004113a  jz      short loc_180041118
0x18004113c  cmp     byte ptr [rcx+19h], 2
0x180041140  jb      short loc_180041118
0x180041142  mov     edx, 20h ; ' '
0x180041147  mov     r9d, 80041008h
0x18004114d  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x180041154  mov     rcx, [rcx+10h]
0x180041158  call    WPP_SF_d
0x18004115d  jmp     short loc_180041118
0x18004115f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041165  mov     edx, 80041008h
0x18004116a  mov     rcx, rax
0x18004116d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041173  lea     rax, WPP_GLOBAL_Control
0x18004117a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041181  cmp     rcx, rax
0x180041184  jz      short loc_1800411AE
0x180041186  test    byte ptr [rcx+1Ch], 1
0x18004118a  jz      short loc_1800411AE
0x18004118c  cmp     byte ptr [rcx+19h], 2
0x180041190  jb      short loc_1800411AE
0x180041192  mov     edx, 21h ; '!'
0x180041197  mov     r9d, 80041008h
0x18004119d  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x1800411a4  mov     rcx, [rcx+10h]
0x1800411a8  call    WPP_SF_d
0x1800411ad  nop
0x1800411ae  lea     rcx, [rsp+88h+var_58]; this
0x1800411b3  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x1800411b8  mov     eax, 80041008h
0x1800411bd  jmp     loc_180041032
0x1800411c2  cmp     byte ptr [rcx+19h], 2
0x1800411c6  jb      loc_180041095
0x1800411cc  mov     edx, 22h ; '"'
0x1800411d1  mov     r9d, 80041005h
0x1800411d7  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x1800411de  mov     rcx, [rcx+10h]
0x1800411e2  call    WPP_SF_d
0x1800411e7  jmp     loc_180041095
0x1800411ec  mov     edi, 80041001h
0x1800411f1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800411f7  mov     edx, edi
0x1800411f9  mov     rcx, rax
0x1800411fc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041202  jmp     loc_180040FF3
0x180041207  mov     eax, 80041006h
0x18004120c  jmp     loc_180041032
```
