# CDefnTypeComp::Bind(ushort *,ulong,ushort,ITypeInfo * *,tagDESCKIND *,tagBINDPTR *)

- ea: `0x1800635f0`
- end: `0x18006394d`
- name: `?Bind@CDefnTypeComp@@UEAAJPEAGKGPEAPEAUITypeInfo@@PEAW4tagDESCKIND@@PEATtagBINDPTR@@@Z`
- size: `861`
- prototype: `int(CDefnTypeComp *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16, struct ITypeInfo **, enum tagDESCKIND *, union tagBINDPTR *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18003e360`
- `0x180052440`
- `0x18005b4d0`
- `0x18005c7c0`
- `0x1800613b8`
- `0x180061470`
- `0x180063130`
- `0x1800632a0`
- `0x1800635f0`
- `0x180063b74`
- `0x180064798`
- `0x1800669b4`
- `0x18006700c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006391b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006391b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800636b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800636b0`

## pseudocode

```c
__int64 __fastcall CDefnTypeComp::Bind(
        CDefnTypeComp *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct ITypeInfo **a5,
        enum tagDESCKIND *a6,
        union tagBINDPTR *a7)
{
  struct ITypeInfo **v9; // r15
  enum tagDESCKIND *v10; // rdi
  union tagBINDPTR *v11; // r14
  unsigned int v12; // r12d
  __int64 result; // rax
  __int64 v14; // rax
  char *v15; // rbx
  __int64 v16; // rsi
  int NamMgr; // ebx
  unsigned int v18; // r8d
  char *v19; // r13
  __int64 v20; // rsi
  int v21; // eax
  int v22; // eax
  struct tagFUNCDESC *v23; // r12
  __int64 v24; // rax
  struct GEN_DTINFO *v25; // rdi
  char *v26; // [rsp+40h] [rbp-41h] BYREF
  NAMMGR *v27; // [rsp+48h] [rbp-39h] BYREF
  struct CDefnTypeComp *v28; // [rsp+50h] [rbp-31h] BYREF
  struct tagFUNCDESC *v29; // [rsp+58h] [rbp-29h] BYREF
  struct tagVARDESC *v30; // [rsp+60h] [rbp-21h] BYREF
  int v31; // [rsp+68h] [rbp-19h] BYREF
  struct DEFN_TYPEBIND *v32[2]; // [rsp+70h] [rbp-11h]
  int v33; // [rsp+80h] [rbp-1h]
  int v34; // [rsp+88h] [rbp+7h]
  unsigned int v36; // [rsp+D8h] [rbp+57h] BYREF

  v31 = 1;
  v33 = -65536;
  v34 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v36 = 0;
  v26 = 0;
  *(_OWORD *)v32 = 0;
  if ( a2 )
  {
    v9 = a5;
    if ( a5 )
    {
      v10 = a6;
      if ( a6 )
      {
        v11 = a7;
        if ( a7 )
        {
          *a5 = 0;
          v12 = a4;
          *v10 = DESCKIND_NONE;
          v11->lpfuncdesc = 0;
          if ( (a4 & 0xFFF0) == 0 )
          {
            result = ConvertStringToA(a2, &v26);
            if ( (int)result < 0 )
              return result;
            EnterCriticalSection(&g_OldFormatCriticalSection);
            v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 1) + 56LL))(
                    *((_QWORD *)this + 1),
                    L"MS-GENPROJ_TYPEBIND");
            v15 = v26;
            v16 = v14;
            if ( v14 )
            {
              NamMgr = GenericTypeLibOLE::GetNamMgr((GenericTypeLibOLE *)(v14 - 312), &v27);
              if ( NamMgr >= 0 )
              {
                v18 = a3;
                v19 = v26;
                NamMgr = NAMMGR::GetHgnamOfStrLhash(v27, v26, v18, &v36);
                if ( NamMgr < 0 )
                  goto LABEL_44;
                if ( v36 )
                {
                  NamMgr = GENPROJ_TYPEBIND::BindProjLevel(v16, 0, v36, v12, 1, 1, *(_DWORD *)(v16 + 24), (__int64)&v31);
                  if ( NamMgr < 0 )
                    goto LABEL_44;
                }
                v20 = 0;
                goto LABEL_18;
              }
            }
            else
            {
              v20 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 1) + 56LL))(
                      *((_QWORD *)this + 1),
                      L"MS-DYN_TYPEBIND");
              NamMgr = NAMMGR::GetHgnamOfStrLhash(*(NAMMGR **)(v20 - 16), v15, a3, &v36);
              if ( NamMgr >= 0 )
              {
                if ( v36 )
                {
                  v21 = DYN_TYPEBIND::BindIdDefn(v20, 0, v36, v12, 1, &v31);
                  v19 = v26;
                  NamMgr = v21;
                  if ( v21 < 0 )
                    goto LABEL_44;
                }
                else
                {
                  v19 = v26;
                }
LABEL_18:
                switch ( v31 )
                {
                  case 1:
                    *v10 = DESCKIND_NONE;
                    break;
                  case 2:
                    v22 = 2;
                    goto LABEL_33;
                  case 3:
                    NamMgr = TYPE_DATA::GetFuncDescOfHfdefn(v32[1], HIWORD(v33), &v29);
                    if ( NamMgr < 0 )
                      goto LABEL_40;
                    v23 = v29;
                    if ( v34 )
                      InterfaceFuncdescToDispatch(v29);
                    v11->lpfuncdesc = v23;
                    *v10 = DESCKIND_FUNCDESC;
                    goto LABEL_35;
                  case 4:
                  case 5:
                  case 6:
                    NamMgr = CDefnTypeComp::Create(&v28, v32[1]);
                    if ( NamMgr < 0 )
                      goto LABEL_40;
                    v11->lpfuncdesc = (FUNCDESC *)v28;
                    *v10 = DESCKIND_TYPECOMP;
                    *v9 = 0;
                    break;
                  case 9:
                    v22 = 4;
LABEL_33:
                    *v10 = v22;
                    NamMgr = TYPE_DATA::GetVarDescOfHvdefn(v32[1], HIWORD(v33), &v30);
                    if ( NamMgr < 0 )
                      goto LABEL_40;
                    v11->lpfuncdesc = (FUNCDESC *)v30;
LABEL_35:
                    if ( !v20 )
                    {
                      v20 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 1) + 56LL))(
                              *((_QWORD *)this + 1),
                              L"MS-DYN_TYPEBIND");
                      if ( !v20 )
                        goto LABEL_41;
                    }
                    v24 = *(_QWORD *)(v20 + 24);
                    v36 = 0;
                    v25 = *(struct GEN_DTINFO **)(v24 + 8);
                    NamMgr = IsFunkyDispinterface(v25, (int *)&v36);
                    if ( NamMgr >= 0 )
                    {
                      if ( v36 )
                      {
                        *v9 = (struct ITypeInfo *)v25;
                        STL_TYPEINFO::AddRef(v25);
                        goto LABEL_40;
                      }
LABEL_41:
                      *v9 = (struct ITypeInfo *)v32[0];
                      break;
                    }
LABEL_40:
                    (*(void (__fastcall **)(struct DEFN_TYPEBIND *))(*(_QWORD *)v32[0] + 16LL))(v32[0]);
                    break;
                }
LABEL_44:
                LeaveCriticalSection(&g_OldFormatCriticalSection);
                ConvertStringFree(v19);
                return (unsigned int)NamMgr;
              }
            }
            v19 = v26;
            goto LABEL_44;
          }
        }
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800635f0  mov     [rsp-8+arg_10], rbx
0x1800635f5  mov     [rsp-8+arg_0], rcx
0x1800635fa  push    rbp
0x1800635fb  push    rsi
0x1800635fc  push    rdi
0x1800635fd  push    r12
0x1800635ff  push    r13
0x180063601  push    r14
0x180063603  push    r15
0x180063605  lea     rbp, [rsp-0Fh]
0x18006360a  sub     rsp, 90h
0x180063611  xor     esi, esi
0x180063613  mov     [rbp+3Fh+var_58], 1
0x18006361a  mov     [rbp+3Fh+var_40], 0FFFF0000h
0x180063621  xorps   xmm0, xmm0
0x180063624  mov     [rbp+3Fh+var_38], esi
0x180063627  mov     r13d, r8d
0x18006362a  mov     [rbp+3Fh+var_60], rsi
0x18006362e  mov     r10, rdx
0x180063631  mov     [rbp+3Fh+var_68], rsi
0x180063635  mov     rbx, rcx
0x180063638  mov     [rbp+3Fh+var_70], rsi
0x18006363c  mov     [rbp+3Fh+var_78], rsi
0x180063640  mov     [rbp+3Fh+arg_8], esi
0x180063643  mov     [rbp+3Fh+var_80], rsi
0x180063647  movdqu  xmmword ptr [rbp+3Fh+var_50], xmm0
0x18006364c  test    rdx, rdx
0x18006364f  jz      loc_18006392D
0x180063655  mov     r15, [rbp+3Fh+arg_20]
0x180063659  test    r15, r15
0x18006365c  jz      loc_18006392D
0x180063662  mov     rdi, [rbp+3Fh+arg_28]
0x180063666  test    rdi, rdi
0x180063669  jz      loc_18006392D
0x18006366f  mov     r14, [rbp+3Fh+arg_30]
0x180063673  test    r14, r14
0x180063676  jz      loc_18006392D
0x18006367c  mov     [r15], rsi
0x18006367f  movzx   r12d, r9w
0x180063683  mov     [rdi], esi
0x180063685  mov     [r14], rsi
0x180063688  test    r12d, 0FFFFFFF0h
0x18006368f  jnz     loc_18006392D
0x180063695  lea     rdx, [rbp+3Fh+var_80]; char **
0x180063699  mov     rcx, r10; lpWideCharStr
0x18006369c  call    ?ConvertStringToA@@YAJPEBGPEAPEAD@Z; ConvertStringToA(ushort const *,char * *)
0x1800636a1  test    eax, eax
0x1800636a3  js      loc_180063932
0x1800636a9  lea     rcx, ?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800636b0  call    cs:__imp_EnterCriticalSection
0x1800636b6  mov     rcx, [rbx+8]
0x1800636ba  lea     rdx, aMsGenprojTypeb; "MS-GENPROJ_TYPEBIND"
0x1800636c1  mov     rax, [rcx]
0x1800636c4  mov     rax, [rax+38h]
0x1800636c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636cd  mov     rbx, [rbp+3Fh+var_80]
0x1800636d1  mov     rsi, rax
0x1800636d4  mov     [rbp+3Fh+var_80], rbx
0x1800636d8  test    rax, rax
0x1800636db  jz      short loc_180063759
0x1800636dd  lea     rcx, [rax-138h]; this
0x1800636e4  lea     rdx, [rbp+3Fh+var_78]; struct NAMMGR **
0x1800636e8  call    ?GetNamMgr@GenericTypeLibOLE@@QEAAJPEAPEAVNAMMGR@@@Z; GenericTypeLibOLE::GetNamMgr(NAMMGR * *)
0x1800636ed  mov     ebx, eax
0x1800636ef  test    eax, eax
0x1800636f1  js      loc_180063910
0x1800636f7  mov     rcx, [rbp+3Fh+var_78]; this
0x1800636fb  lea     r9, [rbp+3Fh+arg_8]; unsigned int *
0x1800636ff  mov     r8d, r13d; unsigned int
0x180063702  mov     r13, [rbp+3Fh+var_80]
0x180063706  mov     rdx, r13; char *
0x180063709  call    ?GetHgnamOfStrLhash@NAMMGR@@QEAAJPEADKPEAK@Z; NAMMGR::GetHgnamOfStrLhash(char *,ulong,ulong *)
0x18006370e  mov     ebx, eax
0x180063710  test    eax, eax
0x180063712  js      loc_180063914
0x180063718  mov     r8d, [rbp+3Fh+arg_8]
0x18006371c  test    r8d, r8d
0x18006371f  jz      short loc_180063755
0x180063721  lea     rax, [rbp+3Fh+var_58]
0x180063725  mov     r9d, r12d
0x180063728  mov     [rsp+0C0h+var_88], rax
0x18006372d  xor     edx, edx
0x18006372f  mov     eax, [rsi+18h]
0x180063732  mov     rcx, rsi
0x180063735  mov     [rsp+0C0h+var_90], eax
0x180063739  mov     eax, 1
0x18006373e  mov     dword ptr [rsp+0C0h+var_98], eax
0x180063742  mov     [rsp+0C0h+var_A0], eax
0x180063746  call    ?BindProjLevel@GENPROJ_TYPEBIND@@QEAAJHKIW4ACCESS@@0W4COMPSTATE@@PEAVEXBIND@@@Z; GENPROJ_TYPEBIND::BindProjLevel(int,ulong,uint,ACCESS,ACCESS,COMPSTATE,EXBIND *)
0x18006374b  mov     ebx, eax
0x18006374d  test    eax, eax
0x18006374f  js      loc_180063914
0x180063755  xor     esi, esi
0x180063757  jmp     short loc_1800637CF
0x180063759  mov     rcx, [rbp+3Fh+arg_0]
0x18006375d  lea     rdx, aMsDynTypebind; "MS-DYN_TYPEBIND"
0x180063764  mov     rcx, [rcx+8]
0x180063768  mov     rax, [rcx]
0x18006376b  mov     rax, [rax+38h]
0x18006376f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063774  lea     r9, [rbp+3Fh+arg_8]; unsigned int *
0x180063778  mov     r8d, r13d; unsigned int
0x18006377b  mov     rdx, rbx; char *
0x18006377e  mov     rsi, rax
0x180063781  mov     rcx, [rax-10h]; this
0x180063785  call    ?GetHgnamOfStrLhash@NAMMGR@@QEAAJPEADKPEAK@Z; NAMMGR::GetHgnamOfStrLhash(char *,ulong,ulong *)
0x18006378a  mov     ebx, eax
0x18006378c  test    eax, eax
0x18006378e  js      loc_180063910
0x180063794  mov     r8d, [rbp+3Fh+arg_8]
0x180063798  test    r8d, r8d
0x18006379b  jz      short loc_1800637CB
0x18006379d  lea     rax, [rbp+3Fh+var_58]
0x1800637a1  mov     r9d, r12d
0x1800637a4  mov     [rsp+0C0h+var_98], rax
0x1800637a9  xor     edx, edx
0x1800637ab  mov     rcx, rsi
0x1800637ae  mov     [rsp+0C0h+var_A0], 1
0x1800637b6  call    ?BindIdDefn@DYN_TYPEBIND@@QEAAJHKIW4ACCESS@@PEAVEXBIND@@@Z; DYN_TYPEBIND::BindIdDefn(int,ulong,uint,ACCESS,EXBIND *)
0x1800637bb  mov     r13, [rbp+3Fh+var_80]
0x1800637bf  mov     ebx, eax
0x1800637c1  test    eax, eax
0x1800637c3  js      loc_180063914
0x1800637c9  jmp     short loc_1800637CF
0x1800637cb  mov     r13, [rbp+3Fh+var_80]
0x1800637cf  mov     ecx, [rbp+3Fh+var_58]
0x1800637d2  sub     ecx, 1
0x1800637d5  jz      loc_180063908
0x1800637db  sub     ecx, 1
0x1800637de  jz      loc_18006386E
0x1800637e4  sub     ecx, 1
0x1800637e7  jz      short loc_180063836
0x1800637e9  sub     ecx, 1
0x1800637ec  jz      short loc_180063806
0x1800637ee  sub     ecx, 1
0x1800637f1  jz      short loc_180063806
0x1800637f3  sub     ecx, 1
0x1800637f6  jz      short loc_180063806
0x1800637f8  cmp     ecx, 3
0x1800637fb  jnz     loc_180063914
0x180063801  lea     eax, [rcx+1]
0x180063804  jmp     short loc_180063873
0x180063806  mov     rdx, [rbp+3Fh+var_50+8]; struct DEFN_TYPEBIND *
0x18006380a  lea     rcx, [rbp+3Fh+var_70]; struct CDefnTypeComp **
0x18006380e  call    ?Create@CDefnTypeComp@@SAJPEAPEAV1@PEAVDEFN_TYPEBIND@@@Z; CDefnTypeComp::Create(CDefnTypeComp * *,DEFN_TYPEBIND *)
0x180063813  mov     ebx, eax
0x180063815  test    eax, eax
0x180063817  js      loc_1800638ED
0x18006381d  mov     rax, [rbp+3Fh+var_70]
0x180063821  mov     [r14], rax
0x180063824  mov     dword ptr [rdi], 3
0x18006382a  mov     qword ptr [r15], 0
0x180063831  jmp     loc_180063914
0x180063836  movzx   edx, word ptr [rbp+3Fh+var_40+2]; unsigned int
0x18006383a  lea     r8, [rbp+3Fh+var_68]; struct tagFUNCDESC **
0x18006383e  mov     rcx, [rbp+3Fh+var_50+8]; this
0x180063842  call    ?GetFuncDescOfHfdefn@TYPE_DATA@@QEAAJIPEAPEAUtagFUNCDESC@@@Z; TYPE_DATA::GetFuncDescOfHfdefn(uint,tagFUNCDESC * *)
0x180063847  mov     ebx, eax
0x180063849  test    eax, eax
0x18006384b  js      loc_1800638ED
0x180063851  cmp     [rbp+3Fh+var_38], 0
0x180063855  mov     r12, [rbp+3Fh+var_68]
0x180063859  jz      short loc_180063863
0x18006385b  mov     rcx, r12; struct tagFUNCDESC *
0x18006385e  call    ?InterfaceFuncdescToDispatch@@YAXPEAUtagFUNCDESC@@@Z; InterfaceFuncdescToDispatch(tagFUNCDESC *)
0x180063863  mov     [r14], r12
0x180063866  mov     dword ptr [rdi], 1
0x18006386c  jmp     short loc_180063893
0x18006386e  mov     eax, 2
0x180063873  mov     [rdi], eax
0x180063875  lea     r8, [rbp+3Fh+var_60]; struct tagVARDESC **
0x180063879  movzx   edx, word ptr [rbp+3Fh+var_40+2]; unsigned int
0x18006387d  mov     rcx, [rbp+3Fh+var_50+8]; this
0x180063881  call    ?GetVarDescOfHvdefn@TYPE_DATA@@QEAAJIPEAPEAUtagVARDESC@@@Z; TYPE_DATA::GetVarDescOfHvdefn(uint,tagVARDESC * *)
0x180063886  mov     ebx, eax
0x180063888  test    eax, eax
0x18006388a  js      short loc_1800638ED
0x18006388c  mov     rax, [rbp+3Fh+var_60]
0x180063890  mov     [r14], rax
0x180063893  test    rsi, rsi
0x180063896  jnz     short loc_1800638BB
0x180063898  mov     rax, [rbp+3Fh+arg_0]
0x18006389c  lea     rdx, aMsDynTypebind; "MS-DYN_TYPEBIND"
0x1800638a3  mov     rcx, [rax+8]
0x1800638a7  mov     rax, [rcx]
0x1800638aa  mov     rax, [rax+38h]
0x1800638ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638b3  mov     rsi, rax
0x1800638b6  test    rax, rax
0x1800638b9  jz      short loc_1800638FF
0x1800638bb  mov     rax, [rsi+18h]
0x1800638bf  lea     rdx, [rbp+3Fh+arg_8]; int *
0x1800638c3  mov     [rbp+3Fh+arg_8], 0
0x1800638ca  mov     rdi, [rax+8]
0x1800638ce  mov     rcx, rdi; struct GEN_DTINFO *
0x1800638d1  call    ?IsFunkyDispinterface@@YAJPEAVGEN_DTINFO@@PEAH@Z; IsFunkyDispinterface(GEN_DTINFO *,int *)
0x1800638d6  mov     ebx, eax
0x1800638d8  test    eax, eax
0x1800638da  js      short loc_1800638ED
0x1800638dc  cmp     [rbp+3Fh+arg_8], 0
0x1800638e0  jz      short loc_1800638FF
0x1800638e2  mov     rcx, rdi; this
0x1800638e5  mov     [r15], rdi
0x1800638e8  call    ?AddRef@STL_TYPEINFO@@UEAAKXZ; STL_TYPEINFO::AddRef(void)
0x1800638ed  mov     rcx, [rbp+3Fh+var_50]
0x1800638f1  mov     rax, [rcx]
0x1800638f4  mov     rax, [rax+10h]
0x1800638f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638fd  jmp     short loc_180063914
0x1800638ff  mov     rax, [rbp+3Fh+var_50]
0x180063903  mov     [r15], rax
0x180063906  jmp     short loc_180063914
0x180063908  mov     dword ptr [rdi], 0
0x18006390e  jmp     short loc_180063914
0x180063910  mov     r13, [rbp+3Fh+var_80]
0x180063914  lea     rcx, ?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006391b  call    cs:__imp_LeaveCriticalSection
0x180063921  mov     rcx, r13; char *
0x180063924  call    ?ConvertStringFree@@YAXPEAD@Z; ConvertStringFree(char *)
0x180063929  mov     eax, ebx
0x18006392b  jmp     short loc_180063932
0x18006392d  mov     eax, 80070057h
0x180063932  mov     rbx, [rsp+0C0h+arg_10]
0x18006393a  add     rsp, 90h
0x180063941  pop     r15
0x180063943  pop     r14
0x180063945  pop     r13
0x180063947  pop     r12
0x180063949  pop     rdi
0x18006394a  pop     rsi
0x18006394b  pop     rbp
0x18006394c  retn
```
