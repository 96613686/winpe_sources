# GetEntryPointPath

- ea: `0x180007130`
- end: `0x1800072de`
- name: `GetEntryPointPath`
- size: `430`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180002850`
- `0x180002af8`
- `0x180007130`
- `0x180008a14`
- `0x180008d34`
- `0x18000ab8c`
- `0x180010d18`
- `0x180012b30`
- `0x180012bd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetEntryPointPath(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  int ApplicationEntryPointFilePath; // ebx
  const struct std::nothrow_t *v6; // rdx
  const struct std::nothrow_t *v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  const struct std::nothrow_t *v9; // rdx
  void **v11; // [rsp+20h] [rbp-E0h] BYREF
  void **v12; // [rsp+28h] [rbp-D8h]
  void *v13; // [rsp+30h] [rbp-D0h]
  int v14; // [rsp+38h] [rbp-C8h]
  int v15; // [rsp+40h] [rbp-C0h]
  unsigned int v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[240]; // [rsp+50h] [rbp-B0h] BYREF

  v16 = a3;
  ApplicationEntryPointFilePath = CheckUrlLengthLimit(a1);
  if ( ApplicationEntryPointFilePath >= 0 )
  {
    v11 = &Dfdll::CString::`vftable';
    v13 = 0;
    v14 = 0;
    v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    v15 = 0;
    Dfdll::CSubscription::CSubscription((Dfdll::CSubscription *)v17);
    ApplicationEntryPointFilePath = Dfdll::CSubscription::LoadFromShortcut((Dfdll::CSubscription *)v17, a1);
    if ( ApplicationEntryPointFilePath >= 0 )
    {
      ApplicationEntryPointFilePath = Dfdll::CSubscription::GetApplicationEntryPointFilePath(
                                        (Dfdll::CSubscription *)v17,
                                        (struct Dfdll::CString *)&v11);
      if ( ApplicationEntryPointFilePath >= 0 )
      {
        if ( v13 )
        {
          ApplicationEntryPointFilePath = Dfdll::CString::CopyTo((Dfdll::CString *)&v11, a2, &v16);
          if ( ApplicationEntryPointFilePath >= 0 )
          {
            ApplicationEntryPointFilePath = 0;
            Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v17);
            v11 = &Dfdll::CString::`vftable';
            v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( v13 )
              operator delete(v13, v9);
          }
          else
          {
            Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v17);
            v11 = &Dfdll::CString::`vftable';
            v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( v13 )
              operator delete(v13, v8);
          }
        }
        else
        {
          ApplicationEntryPointFilePath = -2147024809;
          Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v17);
          v11 = &Dfdll::CString::`vftable';
          v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v13 )
            operator delete(v13, v7);
        }
      }
      else
      {
        Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v17);
        v11 = &Dfdll::CString::`vftable';
        v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v13 )
          operator delete(v13, v6);
      }
    }
    else
    {
      Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v17);
      v11 = &Dfdll::CString::`vftable';
      v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    }
  }
  return (unsigned int)ApplicationEntryPointFilePath;
}

```

## disassembly

```asm
0x180007130  mov     [rsp-8+arg_18], rbx
0x180007135  push    rbp
0x180007136  push    rsi
0x180007137  push    rdi
0x180007138  push    r12
0x18000713a  push    r15
0x18000713c  lea     rbp, [rsp-50h]
0x180007141  sub     rsp, 150h
0x180007148  mov     rax, cs:__security_cookie
0x18000714f  xor     rax, rsp
0x180007152  mov     [rbp+70h+var_30], rax
0x180007156  mov     rsi, rdx
0x180007159  mov     rdi, rcx
0x18000715c  mov     [rsp+170h+var_128], r8d
0x180007161  call    ?CheckUrlLengthLimit@@YAJPEBG@Z; CheckUrlLengthLimit(ushort const *)
0x180007166  mov     ebx, eax
0x180007168  test    eax, eax
0x18000716a  js      loc_1800072B9
0x180007170  lea     r15, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180007177  mov     [rsp+170h+var_150], r15
0x18000717c  and     [rsp+170h+var_140], 0
0x180007182  and     [rsp+170h+var_138], 0
0x180007187  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000718e  mov     [rsp+170h+var_148], r12
0x180007193  and     [rsp+170h+var_130], 0
0x180007198  lea     rcx, [rsp+170h+var_120]; this
0x18000719d  call    ??0CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::CSubscription(void)
0x1800071a2  nop
0x1800071a3  mov     rdx, rdi; unsigned __int16 *
0x1800071a6  lea     rcx, [rsp+170h+var_120]; this
0x1800071ab  call    ?LoadFromShortcut@CSubscription@Dfdll@@QEAAJPEBG@Z; Dfdll::CSubscription::LoadFromShortcut(ushort const *)
0x1800071b0  mov     ebx, eax
0x1800071b2  test    eax, eax
0x1800071b4  jns     short loc_1800071E0
0x1800071b6  lea     rcx, [rsp+170h+var_120]; this
0x1800071bb  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x1800071c0  nop
0x1800071c1  mov     [rsp+170h+var_150], r15
0x1800071c6  mov     [rsp+170h+var_148], r12
0x1800071cb  mov     rcx, [rsp+170h+var_140]; void *
0x1800071d0  test    rcx, rcx
0x1800071d3  jz      short loc_1800071DB
0x1800071d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800071da  nop
0x1800071db  jmp     loc_1800072B9
0x1800071e0  lea     rdx, [rsp+170h+var_150]; struct Dfdll::CString *
0x1800071e5  lea     rcx, [rsp+170h+var_120]; this
0x1800071ea  call    ?GetApplicationEntryPointFilePath@CSubscription@Dfdll@@QEAAJAEAVCString@2@@Z; Dfdll::CSubscription::GetApplicationEntryPointFilePath(Dfdll::CString &)
0x1800071ef  mov     ebx, eax
0x1800071f1  test    eax, eax
0x1800071f3  jns     short loc_18000721F
0x1800071f5  lea     rcx, [rsp+170h+var_120]; this
0x1800071fa  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x1800071ff  nop
0x180007200  mov     [rsp+170h+var_150], r15
0x180007205  mov     [rsp+170h+var_148], r12
0x18000720a  mov     rcx, [rsp+170h+var_140]; void *
0x18000720f  test    rcx, rcx
0x180007212  jz      short loc_18000721A
0x180007214  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007219  nop
0x18000721a  jmp     loc_1800072B9
0x18000721f  cmp     [rsp+170h+var_140], 0
0x180007225  jnz     short loc_180007253
0x180007227  mov     ebx, 80070057h
0x18000722c  lea     rcx, [rsp+170h+var_120]; this
0x180007231  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x180007236  nop
0x180007237  mov     [rsp+170h+var_150], r15
0x18000723c  mov     [rsp+170h+var_148], r12
0x180007241  mov     rcx, [rsp+170h+var_140]; void *
0x180007246  test    rcx, rcx
0x180007249  jz      short loc_180007251
0x18000724b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007250  nop
0x180007251  jmp     short loc_1800072B9
0x180007253  lea     r8, [rsp+170h+var_128]; unsigned int *
0x180007258  mov     rdx, rsi; unsigned __int16 *
0x18000725b  lea     rcx, [rsp+170h+var_150]; this
0x180007260  call    ?CopyTo@CString@Dfdll@@QEAAJPEAGAEAI@Z; Dfdll::CString::CopyTo(ushort *,uint &)
0x180007265  mov     ebx, eax
0x180007267  test    eax, eax
0x180007269  jns     short loc_180007292
0x18000726b  lea     rcx, [rsp+170h+var_120]; this
0x180007270  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x180007275  nop
0x180007276  mov     [rsp+170h+var_150], r15
0x18000727b  mov     [rsp+170h+var_148], r12
0x180007280  mov     rcx, [rsp+170h+var_140]; void *
0x180007285  test    rcx, rcx
0x180007288  jz      short loc_180007290
0x18000728a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000728f  nop
0x180007290  jmp     short loc_1800072B9
0x180007292  xor     ebx, ebx
0x180007294  lea     rcx, [rsp+170h+var_120]; this
0x180007299  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x18000729e  nop
0x18000729f  mov     [rsp+170h+var_150], r15
0x1800072a4  mov     [rsp+170h+var_148], r12
0x1800072a9  mov     rcx, [rsp+170h+var_140]; void *
0x1800072ae  test    rcx, rcx
0x1800072b1  jz      short loc_1800072B9
0x1800072b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800072b8  nop
0x1800072b9  mov     eax, ebx
0x1800072bb  mov     rcx, [rbp+70h+var_30]
0x1800072bf  xor     rcx, rsp; StackCookie
0x1800072c2  call    __security_check_cookie
0x1800072c7  mov     rbx, [rsp+170h+arg_18]
0x1800072cf  add     rsp, 150h
0x1800072d6  pop     r15
0x1800072d8  pop     r12
0x1800072da  pop     rdi
0x1800072db  pop     rsi
0x1800072dc  pop     rbp
0x1800072dd  retn
```
