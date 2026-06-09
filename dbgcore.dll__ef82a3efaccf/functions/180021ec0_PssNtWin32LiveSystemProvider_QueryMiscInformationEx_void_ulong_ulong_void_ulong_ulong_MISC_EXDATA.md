# PssNtWin32LiveSystemProvider::QueryMiscInformationEx(void *,ulong,ulong *,void *,ulong,ulong *,MISC_EXDATA *)

- ea: `0x180021ec0`
- end: `0x1800222bc`
- name: `?QueryMiscInformationEx@PssNtWin32LiveSystemProvider@@UEAAJPEAXKPEAK0K1PEAUMISC_EXDATA@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(PssNtWin32LiveSystemProvider *__hidden this, void *, unsigned int, unsigned int *, void *, unsigned int, unsigned int *, struct MISC_EXDATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180021e80`

## callees

- `0x180001710`
- `0x180002194`
- `0x1800021a0`
- `0x1800021f4`
- `0x180005e44`
- `0x180021ec0`
- `0x180025710`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022146`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002213e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002213e`

## pseudocode

```c
__int64 __fastcall PssNtWin32LiveSystemProvider::QueryMiscInformationEx(
        __int64 (__fastcall **this)(char *),
        __int64 (__fastcall *a2)(char *),
        unsigned int a3,
        unsigned int *a4,
        char *a5,
        unsigned int a6,
        unsigned int *a7,
        struct MISC_EXDATA *a8)
{
  __int64 (__fastcall *v13)(char *); // rax
  int v14; // eax
  __int64 (__fastcall *v15)(char *); // rcx
  __int64 (__fastcall *v16)(char *); // rax
  signed int v17; // eax
  bool v18; // cc
  signed int LastError; // eax
  _QWORD *v20; // rax
  _QWORD *v21; // r15
  __int64 (__fastcall *v22)(char *); // rbx
  _BYTE *v23; // rax
  signed int v24; // eax
  int v25; // eax
  unsigned int v26; // ebx
  __int64 (__fastcall *v27)(char *); // rax
  __int64 (__fastcall *v28)(char *); // rax
  __int64 v29; // r8
  unsigned int v30; // r8d
  size_t *p_Size; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[236]; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+14Ch] [rbp+4Ch]
  _BYTE v37[176]; // [rsp+150h] [rbp+50h] BYREF
  int v38; // [rsp+200h] [rbp+100h]
  _XSTATE_CONFIGURATION v39; // [rsp+410h] [rbp+310h] BYREF

  v34 = 0;
  memset_0(v37, 0, 0x2C0u);
  memset_0(v35, 0, 0xF0u);
  LODWORD(Size) = 0;
  if ( this[153] != a2 )
    return NtWin32LiveSystemProvider::QueryMiscInformationEx(
             (NtWin32LiveSystemProvider *)this,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8);
  *a4 = 0;
  if ( a7 )
    *a7 = 1364;
  if ( !a5 || a6 < 0x554 )
    return (unsigned int)-2147024662;
  v13 = this[44];
  if ( v13 )
  {
    v14 = v13(a5 + 60);
    *((_DWORD *)a5 + 14) = v14;
    if ( v14 == -1 )
      *((_DWORD *)a5 + 15) = GetLastError();
    else
      *a4 |= 0x40u;
  }
  *((_DWORD *)a5 + 340) = 0;
  *((_DWORD *)a5 + 11) = -2147023728;
  *((_DWORD *)a5 + 12) = -2147023728;
  if ( !this[126] || !this[127] || !this[128] )
  {
    *((_DWORD *)a5 + 11) = -2147467263;
    goto LABEL_34;
  }
  v15 = this[153];
  v16 = this[142];
  hObject = 0;
  v17 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(char *), __int64, __int64 *))v16)(v15, 1, &v34);
  v18 = v17 <= 0;
  if ( !v17 )
  {
    if ( ((unsigned int (__fastcall *)(__int64, __int64, HANDLE *))this[125])(v34, 8, &hObject) )
    {
      p_Size = &Size;
      ((void (__fastcall *)(HANDLE, __int64, _QWORD))this[126])(hObject, 25, 0);
      LastError = GetLastError();
      *((_DWORD *)a5 + 11) = LastError;
      if ( LastError == 122 )
      {
        v20 = o_malloc_0((unsigned int)Size);
        v21 = v20;
        if ( v20 )
        {
          if ( ((unsigned int (__fastcall *)(HANDLE, __int64, _QWORD *, _QWORD, size_t *))this[126])(
                 hObject,
                 25,
                 v20,
                 (unsigned int)Size,
                 &Size) )
          {
            v22 = this[127];
            v23 = (_BYTE *)this[128]((char *)*v21);
            *((_DWORD *)a5 + 11) = *(_DWORD *)((__int64 (__fastcall *)(_QWORD, _QWORD))v22)(
                                                *v21,
                                                (unsigned __int8)(*v23 - 1));
            *a4 |= 0x10u;
          }
          else
          {
            v24 = GetLastError();
            if ( v24 > 0 )
              v24 = (unsigned __int16)v24 | 0x80070000;
            *((_DWORD *)a5 + 11) = v24;
          }
          free(v21);
        }
        else
        {
          *((_DWORD *)a5 + 11) = -2147024882;
        }
      }
      else
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        *((_DWORD *)a5 + 11) = LastError;
      }
      CloseHandle(hObject);
      goto LABEL_34;
    }
    v17 = GetLastError();
    v18 = v17 <= 0;
  }
  if ( !v18 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  *((_DWORD *)a5 + 11) = v17;
LABEL_34:
  v25 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(char *), _QWORD, _BYTE *, __int64))this[142])(
          this[153],
          0,
          v37,
          704);
  v26 = v25;
  if ( v25 )
  {
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    *((_DWORD *)a5 + 13) = v26;
  }
  else
  {
    v26 = 0;
    *((_DWORD *)a5 + 12) = v38;
    *((_DWORD *)a5 + 13) = v37[36] & 1;
    *a4 |= 0xA0u;
  }
  v27 = this[150];
  if ( v27
    && ((int (__fastcall *)(__int64 (__fastcall *)(char *), _QWORD, _BYTE *, __int64))v27)(this[153], 0, v35, 240) >= 0 )
  {
    *a4 |= 0x200u;
    *((_DWORD *)a5 + 340) = v36;
  }
  if ( !a8 || (*(_DWORD *)a8 & 0x200000) == 0 )
    return v26;
  memset_0(&v39, 0, 0x358u);
  v28 = *this;
  v29 = *((_QWORD *)a8 + 1);
  LODWORD(hObject) = 0;
  LODWORD(p_Size) = 856;
  if ( !(*((unsigned int (__fastcall **)(__int64 (__fastcall **)(char *), __int64 (__fastcall *)(char *), __int64, _XSTATE_CONFIGURATION *, size_t *, HANDLE *))v28
         + 29))(
          this,
          a2,
          v29,
          &v39,
          p_Size,
          &hObject)
    && (_DWORD)hObject == 856 )
  {
    if ( (v39.EnabledFeatures & 0xE4) != 0 || (v39.EnabledUserVisibleSupervisorFeatures & 0x800) != 0 )
    {
      CopyXStateConfigToMiscInfo(&v39, (struct _XSTATE_CONFIG_FEATURE_MSC_INFO *)(a5 + 832), v30);
      *((_DWORD *)a5 + 209) = *((_DWORD *)a8 + 4);
    }
    return v26;
  }
  return (unsigned int)-2147024662;
}

```

## disassembly

```asm
0x180021ec0  mov     [rsp-8+arg_10], rbx
0x180021ec5  push    rbp
0x180021ec6  push    rsi
0x180021ec7  push    rdi
0x180021ec8  push    r12
0x180021eca  push    r13
0x180021ecc  push    r14
0x180021ece  push    r15
0x180021ed0  lea     rbp, [rsp-680h]
0x180021ed8  sub     rsp, 780h
0x180021edf  mov     rax, cs:__security_cookie
0x180021ee6  xor     rax, rsp
0x180021ee9  mov     [rbp+6B0h+var_40], rax
0x180021ef0  mov     r13, [rbp+6B0h+arg_38]
0x180021ef7  mov     r15d, r8d
0x180021efa  mov     rdi, [rbp+6B0h+arg_20]
0x180021f01  mov     r12, rdx
0x180021f04  mov     rbx, [rbp+6B0h+arg_30]
0x180021f0b  mov     rsi, rcx
0x180021f0e  xor     edx, edx; Val
0x180021f10  mov     [rsp+7B0h+var_760], 0
0x180021f19  mov     r8d, 2C0h; Size
0x180021f1f  lea     rcx, [rbp+6B0h+var_660]; void *
0x180021f23  mov     r14, r9
0x180021f26  call    memset_0
0x180021f2b  xor     edx, edx; Val
0x180021f2d  lea     rcx, [rsp+7B0h+var_750]; void *
0x180021f32  mov     r8d, 0F0h; Size
0x180021f38  call    memset_0
0x180021f3d  mov     dword ptr [rsp+7B0h+Size], 0
0x180021f45  cmp     [rsi+4C8h], r12
0x180021f4c  jz      short loc_180021F7D
0x180021f4e  mov     eax, [rbp+6B0h+arg_28]
0x180021f54  mov     r9, r14; unsigned int *
0x180021f57  mov     [rsp+7B0h+var_778], r13; struct MISC_EXDATA *
0x180021f5c  mov     r8d, r15d; unsigned int
0x180021f5f  mov     [rsp+7B0h+var_780], rbx; unsigned int *
0x180021f64  mov     rdx, r12; void *
0x180021f67  mov     [rsp+7B0h+var_788], eax; unsigned int
0x180021f6b  mov     rcx, rsi; this
0x180021f6e  mov     [rsp+7B0h+var_790], rdi; void *
0x180021f73  call    ?QueryMiscInformationEx@NtWin32LiveSystemProvider@@UEAAJPEAXKPEAK0K1PEAUMISC_EXDATA@@@Z; NtWin32LiveSystemProvider::QueryMiscInformationEx(void *,ulong,ulong *,void *,ulong,ulong *,MISC_EXDATA *)
0x180021f78  jmp     loc_180022292
0x180021f7d  xor     r15d, r15d
0x180021f80  mov     eax, 554h
0x180021f85  mov     [r14], r15d
0x180021f88  test    rbx, rbx
0x180021f8b  jz      short loc_180021F8F
0x180021f8d  mov     [rbx], eax
0x180021f8f  test    rdi, rdi
0x180021f92  jz      loc_18002228B
0x180021f98  cmp     [rbp+6B0h+arg_28], eax
0x180021f9e  jb      loc_18002228B
0x180021fa4  mov     rax, [rsi+160h]
0x180021fab  test    rax, rax
0x180021fae  jz      short loc_180021FD0
0x180021fb0  lea     rcx, [rdi+3Ch]
0x180021fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb9  mov     [rdi+38h], eax
0x180021fbc  cmp     eax, 0FFFFFFFFh
0x180021fbf  jz      short loc_180021FC7
0x180021fc1  or      dword ptr [r14], 40h
0x180021fc5  jmp     short loc_180021FD0
0x180021fc7  call    cs:__imp_GetLastError
0x180021fcd  mov     [rdi+3Ch], eax
0x180021fd0  mov     eax, 80070490h
0x180021fd5  mov     [rdi+550h], r15d
0x180021fdc  mov     [rdi+2Ch], eax
0x180021fdf  mov     ebx, 80070000h
0x180021fe4  mov     [rdi+30h], eax
0x180021fe7  cmp     [rsi+3F0h], r15
0x180021fee  jz      loc_18002215A
0x180021ff4  cmp     [rsi+3F8h], r15
0x180021ffb  jz      loc_18002215A
0x180022001  cmp     [rsi+400h], r15
0x180022008  jz      loc_18002215A
0x18002200e  mov     rcx, [rsi+4C8h]
0x180022015  lea     r8, [rsp+7B0h+var_760]
0x18002201a  mov     rax, [rsi+470h]
0x180022021  mov     r9d, 8
0x180022027  mov     [rsp+7B0h+hObject], r15
0x18002202c  lea     edx, [r9-7]
0x180022030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022035  test    eax, eax
0x180022037  jnz     loc_18002214E
0x18002203d  mov     rcx, [rsp+7B0h+var_760]
0x180022042  lea     edx, [rax+8]
0x180022045  mov     rax, [rsi+3E8h]
0x18002204c  lea     r8, [rsp+7B0h+hObject]
0x180022051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022056  test    eax, eax
0x180022058  jz      loc_180022146
0x18002205e  mov     rcx, [rsp+7B0h+hObject]
0x180022063  lea     rax, [rsp+7B0h+Size]
0x180022068  xor     r9d, r9d
0x18002206b  mov     [rsp+7B0h+var_790], rax
0x180022070  mov     rax, [rsi+3F0h]
0x180022077  xor     r8d, r8d
0x18002207a  lea     edx, [r9+19h]
0x18002207e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022083  call    cs:__imp_GetLastError
0x180022089  mov     [rdi+2Ch], eax
0x18002208c  cmp     eax, 7Ah ; 'z'
0x18002208f  jnz     loc_18002212D
0x180022095  mov     ecx, dword ptr [rsp+7B0h+Size]; Size
0x180022099  call    _o_malloc_0
0x18002209e  mov     r15, rax
0x1800220a1  test    rax, rax
0x1800220a4  jz      short loc_180022121
0x1800220a6  mov     r9d, dword ptr [rsp+7B0h+Size]
0x1800220ab  lea     rax, [rsp+7B0h+Size]
0x1800220b0  mov     rcx, [rsp+7B0h+hObject]
0x1800220b5  mov     r8, r15
0x1800220b8  mov     [rsp+7B0h+var_790], rax
0x1800220bd  mov     edx, 19h
0x1800220c2  mov     rax, [rsi+3F0h]
0x1800220c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ce  test    eax, eax
0x1800220d0  jz      short loc_180022105
0x1800220d2  mov     rcx, [r15]
0x1800220d5  mov     rax, [rsi+400h]
0x1800220dc  mov     rbx, [rsi+3F8h]
0x1800220e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e8  mov     cl, [rax]
0x1800220ea  mov     rax, rbx
0x1800220ed  dec     cl
0x1800220ef  movzx   edx, cl
0x1800220f2  mov     rcx, [r15]
0x1800220f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220fa  mov     ecx, [rax]
0x1800220fc  mov     [rdi+2Ch], ecx
0x1800220ff  or      dword ptr [r14], 10h
0x180022103  jmp     short loc_180022117
0x180022105  call    cs:__imp_GetLastError
0x18002210b  test    eax, eax
0x18002210d  jle     short loc_180022114
0x18002210f  movzx   eax, ax
0x180022112  or      eax, ebx
0x180022114  mov     [rdi+2Ch], eax
0x180022117  mov     rcx, r15; Block
0x18002211a  call    free
0x18002211f  jmp     short loc_180022128
0x180022121  mov     dword ptr [rdi+2Ch], 8007000Eh
0x180022128  xor     r15d, r15d
0x18002212b  jmp     short loc_180022139
0x18002212d  test    eax, eax
0x18002212f  jle     short loc_180022136
0x180022131  movzx   eax, ax
0x180022134  or      eax, ebx
0x180022136  mov     [rdi+2Ch], eax
0x180022139  mov     rcx, [rsp+7B0h+hObject]; hObject
0x18002213e  call    cs:__imp_CloseHandle
0x180022144  jmp     short loc_180022161
0x180022146  call    cs:__imp_GetLastError
0x18002214c  test    eax, eax
0x18002214e  jle     short loc_180022155
0x180022150  movzx   eax, ax
0x180022153  or      eax, ebx
0x180022155  mov     [rdi+2Ch], eax
0x180022158  jmp     short loc_180022161
0x18002215a  mov     dword ptr [rdi+2Ch], 80004001h
0x180022161  mov     rcx, [rsi+4C8h]
0x180022168  lea     r8, [rbp+6B0h+var_660]
0x18002216c  mov     rax, [rsi+470h]
0x180022173  mov     r9d, 2C0h
0x180022179  xor     edx, edx
0x18002217b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022180  mov     ebx, eax
0x180022182  test    eax, eax
0x180022184  jnz     short loc_1800221A4
0x180022186  mov     eax, [rbp+6B0h+var_5B0]
0x18002218c  mov     ebx, r15d
0x18002218f  mov     [rdi+30h], eax
0x180022192  mov     eax, [rbp+6B0h+var_63C]
0x180022195  and     eax, 1
0x180022198  mov     [rdi+34h], eax
0x18002219b  or      dword ptr [r14], 0A0h
0x1800221a2  jmp     short loc_1800221B2
0x1800221a4  jle     short loc_1800221AF
0x1800221a6  movzx   ebx, ax
0x1800221a9  or      ebx, 80070000h
0x1800221af  mov     [rdi+34h], ebx
0x1800221b2  mov     rax, [rsi+4B0h]
0x1800221b9  test    rax, rax
0x1800221bc  jz      short loc_1800221E9
0x1800221be  mov     rcx, [rsi+4C8h]
0x1800221c5  lea     r8, [rsp+7B0h+var_750]
0x1800221ca  mov     r9d, 0F0h
0x1800221d0  xor     edx, edx
0x1800221d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221d7  test    eax, eax
0x1800221d9  js      short loc_1800221E9
0x1800221db  bts     dword ptr [r14], 9
0x1800221e0  mov     eax, [rbp+6B0h+var_664]
0x1800221e3  mov     [rdi+550h], eax
0x1800221e9  test    r13, r13
0x1800221ec  jz      loc_180022290
0x1800221f2  test    dword ptr [r13+0], 200000h
0x1800221fa  jz      loc_180022290
0x180022200  mov     r14d, 358h
0x180022206  lea     rcx, [rbp+6B0h+var_3A0]; void *
0x18002220d  mov     r8d, r14d; Size
0x180022210  xor     edx, edx; Val
0x180022212  call    memset_0
0x180022217  mov     rax, [rsi]
0x18002221a  lea     rcx, [rsp+7B0h+hObject]
0x18002221f  mov     r8, [r13+8]
0x180022223  lea     r9, [rbp+6B0h+var_3A0]
0x18002222a  mov     qword ptr [rsp+7B0h+var_788], rcx
0x18002222f  mov     rdx, r12
0x180022232  mov     rcx, rsi
0x180022235  mov     dword ptr [rsp+7B0h+hObject], r15d
0x18002223a  mov     rax, [rax+0E8h]
0x180022241  mov     dword ptr [rsp+7B0h+var_790], r14d
0x180022246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002224b  test    eax, eax
0x18002224d  jnz     short loc_18002228B
0x18002224f  cmp     dword ptr [rsp+7B0h+hObject], r14d
0x180022254  jnz     short loc_18002228B
0x180022256  test    byte ptr [rbp+6B0h+var_3A0.EnabledFeatures], 0E4h
0x18002225d  jnz     short loc_18002226C
0x18002225f  test    [rbp+6B0h+var_3A0.EnabledUserVisibleSupervisorFeatures], 800h
0x18002226a  jz      short loc_180022290
0x18002226c  lea     rdx, [rdi+340h]; struct _XSTATE_CONFIG_FEATURE_MSC_INFO *
0x180022273  lea     rcx, [rbp+6B0h+var_3A0]; struct _XSTATE_CONFIGURATION *
0x18002227a  call    ?CopyXStateConfigToMiscInfo@@YAXPEAU_XSTATE_CONFIGURATION@@PEAU_XSTATE_CONFIG_FEATURE_MSC_INFO@@K@Z; CopyXStateConfigToMiscInfo(_XSTATE_CONFIGURATION *,_XSTATE_CONFIG_FEATURE_MSC_INFO *,ulong)
0x18002227f  mov     eax, [r13+10h]
0x180022283  mov     [rdi+344h], eax
0x180022289  jmp     short loc_180022290
0x18002228b  mov     ebx, 800700EAh
0x180022290  mov     eax, ebx
0x180022292  mov     rcx, [rbp+6B0h+var_40]
0x180022299  xor     rcx, rsp; StackCookie
0x18002229c  call    __security_check_cookie
0x1800222a1  mov     rbx, [rsp+7B0h+arg_10]
0x1800222a9  add     rsp, 780h
0x1800222b0  pop     r15
0x1800222b2  pop     r14
0x1800222b4  pop     r13
0x1800222b6  pop     r12
0x1800222b8  pop     rdi
0x1800222b9  pop     rsi
0x1800222ba  pop     rbp
0x1800222bb  retn
```
