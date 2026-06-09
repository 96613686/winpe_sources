# CreateCDirectMusicSynthPort(tagPORTENTRY *,CDirectMusic *,uint,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *)

- ea: `0x1800111fc`
- end: `0x180011401`
- name: `?CreateCDirectMusicSynthPort@@YAJPEAUtagPORTENTRY@@PEAVCDirectMusic@@IPEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@@Z`
- size: `517`
- prototype: `__int64 __usercall@<rax>(struct tagPORTENTRY *@<rcx>, struct CDirectMusic *@<rdx>, unsigned int@<r8d>, struct _DMUS_PORTPARAMS8 *@<r9>, struct IDirectMusicPort **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800131a0`

## callees

- `0x1800111fc`
- `0x180011fc0`
- `0x180016230`
- `0x1800166f4`
- `0x180016c04`
- `0x180017694`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800112c2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011374`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800112c2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011374`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001125b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800112a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001125b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800112a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall CreateCDirectMusicSynthPort(
        struct tagPORTENTRY *a1,
        struct CDirectMusic *a2,
        unsigned int a3,
        struct _DMUS_PORTPARAMS8 *a4,
        struct IDirectMusicPort **a5)
{
  char v8; // r14
  const IID *v9; // r15
  HRESULT Instance; // ebx
  HRESULT result; // eax
  CDirectMusicSynthPort7 *v12; // rax
  struct IDirectMusicPort *v13; // rdi
  CDirectMusicSynthPort8 *v14; // rax
  struct IDirectMusicPort *v15; // rdi
  struct IDirectMusicSynth *v16; // [rsp+30h] [rbp-20h] BYREF
  struct IDirectMusicSynth8 *ppv; // [rsp+38h] [rbp-18h] BYREF
  CDirectMusicSynthPort7 *v18; // [rsp+40h] [rbp-10h]

  v16 = 0;
  ppv = 0;
  v8 = 0;
  if ( a3 < 8 || SLOBYTE(a4->dwValidParams) >= 0 || (a4->dwFeatures & 1) == 0 )
  {
    v9 = (const IID *)((char *)a1 + 40);
    goto LABEL_9;
  }
  v9 = (const IID *)((char *)a1 + 40);
  Instance = CoCreateInstance((const IID *const)((char *)a1 + 40), 0, 1u, &IID_IDirectMusicSynth8, (LPVOID *)&ppv);
  if ( (int)(Instance + 0x80000000) < 0 || Instance == -2147467262 )
  {
    v8 = 1;
    if ( Instance != -2147467262 )
    {
LABEL_10:
      if ( v16 )
      {
        v12 = (CDirectMusicSynthPort7 *)malloc(0x340u);
        v18 = v12;
        if ( v12 )
          v13 = (struct IDirectMusicPort *)CDirectMusicSynthPort7::CDirectMusicSynthPort7(v12, a1, a2, v16);
        else
          v13 = 0;
        if ( v13 )
        {
          Instance = CDirectMusicSynthPort7::Initialize((CDirectMusicSynthPort7 *)v13, a4);
          if ( Instance >= 0 )
          {
            *a5 = v13 + 47;
            ((void (__fastcall *)(struct IDirectMusicPort *))v13[47].lpVtbl->AddRef)(&v13[47]);
          }
          ((void (__fastcall *)(struct IDirectMusicPort *))v13->lpVtbl->Release)(v13);
        }
        else
        {
          Instance = -2147024882;
        }
        if ( v16 )
          ((void (__fastcall *)(struct IDirectMusicSynth *))v16->lpVtbl->Release)(v16);
        if ( Instance >= 0 )
        {
          if ( v8 )
          {
            a4->dwFeatures &= ~1u;
            return 1;
          }
        }
      }
      else if ( ppv )
      {
        v14 = (CDirectMusicSynthPort8 *)malloc(0x368u);
        v18 = v14;
        if ( v14 )
          v15 = (struct IDirectMusicPort *)CDirectMusicSynthPort8::CDirectMusicSynthPort8(v14, a1, a2, ppv);
        else
          v15 = 0;
        if ( v15 )
        {
          Instance = CDirectMusicSynthPort8::Initialize((CDirectMusicSynthPort8 *)v15, a4);
          if ( Instance >= 0 )
          {
            *a5 = v15 + 47;
            ((void (__fastcall *)(struct IDirectMusicPort *))v15[47].lpVtbl->AddRef)(&v15[47]);
          }
          CDirectMusicSynthPort::Release((CDirectMusicSynthPort *)v15);
        }
        else
        {
          Instance = -2147024882;
        }
        if ( ppv )
          ((void (__fastcall *)(struct IDirectMusicSynth8 *))ppv->lpVtbl->Release)(ppv);
      }
      return Instance;
    }
LABEL_9:
    result = CoCreateInstance(v9, 0, 1u, &IID_IDirectMusicSynth, (LPVOID *)&v16);
    Instance = result;
    if ( result < 0 )
      return result;
    goto LABEL_10;
  }
  return Instance;
}

```

## disassembly

```asm
0x1800111fc  push    rbp
0x1800111fe  push    rbx
0x1800111ff  push    rsi
0x180011200  push    rdi
0x180011201  push    r12
0x180011203  push    r14
0x180011205  push    r15
0x180011207  mov     rbp, rsp
0x18001120a  sub     rsp, 50h
0x18001120e  mov     rsi, r9
0x180011211  mov     r12, rdx
0x180011214  mov     rdi, rcx
0x180011217  mov     [rbp+var_20], 0
0x18001121f  mov     [rbp+var_18], 0
0x180011227  xor     r14b, r14b
0x18001122a  cmp     r8d, 8
0x18001122e  jb      short loc_180011285
0x180011230  test    byte ptr [r9+4], 80h
0x180011235  jz      short loc_180011285
0x180011237  test    byte ptr [r9+20h], 1
0x18001123c  jz      short loc_180011285
0x18001123e  lea     r15, [rcx+28h]
0x180011242  lea     rax, [rbp+var_18]
0x180011246  mov     [rsp+50h+ppv], rax; ppv
0x18001124b  lea     r9, IID_IDirectMusicSynth8; riid
0x180011252  xor     edx, edx; pUnkOuter
0x180011254  lea     r8d, [rdx+1]; dwClsContext
0x180011258  mov     rcx, r15; rclsid
0x18001125b  call    cs:__imp_CoCreateInstance
0x180011261  mov     ebx, eax
0x180011263  mov     eax, 80000000h
0x180011268  lea     ecx, [rbx+rax]
0x18001126b  mov     edx, 80004002h
0x180011270  test    eax, ecx
0x180011272  jnz     short loc_18001127C
0x180011274  cmp     ebx, edx
0x180011276  jnz     loc_1800113F0
0x18001127c  mov     r14b, 1
0x18001127f  cmp     ebx, edx
0x180011281  jnz     short loc_1800112B2
0x180011283  jmp     short loc_180011289
0x180011285  lea     r15, [rcx+28h]
0x180011289  lea     rax, [rbp+var_20]
0x18001128d  mov     [rsp+50h+ppv], rax; ppv
0x180011292  lea     r9, IID_IDirectMusicSynth; riid
0x180011299  xor     edx, edx; pUnkOuter
0x18001129b  lea     r8d, [rdx+1]; dwClsContext
0x18001129f  mov     rcx, r15; rclsid
0x1800112a2  call    cs:__imp_CoCreateInstance
0x1800112a8  mov     ebx, eax
0x1800112aa  test    eax, eax
0x1800112ac  js      loc_1800113F2
0x1800112b2  cmp     [rbp+var_20], 0
0x1800112b7  jz      loc_180011364
0x1800112bd  mov     ecx, 340h; Size
0x1800112c2  call    cs:__imp_malloc
0x1800112c8  mov     [rbp+var_10], rax
0x1800112cc  test    rax, rax
0x1800112cf  jz      short loc_1800112E8
0x1800112d1  mov     r9, [rbp+var_20]; struct IDirectMusicSynth *
0x1800112d5  mov     r8, r12; struct CDirectMusic *
0x1800112d8  mov     rdx, rdi; struct tagPORTENTRY *
0x1800112db  mov     rcx, rax; this
0x1800112de  call    ??0CDirectMusicSynthPort7@@QEAA@PEAUtagPORTENTRY@@PEAVCDirectMusic@@PEAUIDirectMusicSynth@@@Z; CDirectMusicSynthPort7::CDirectMusicSynthPort7(tagPORTENTRY *,CDirectMusic *,IDirectMusicSynth *)
0x1800112e3  mov     rdi, rax
0x1800112e6  jmp     short loc_1800112EA
0x1800112e8  xor     edi, edi
0x1800112ea  test    rdi, rdi
0x1800112ed  jnz     short loc_1800112F6
0x1800112ef  mov     ebx, 8007000Eh
0x1800112f4  jmp     short loc_180011330
0x1800112f6  mov     rdx, rsi; struct _DMUS_PORTPARAMS8 *
0x1800112f9  mov     rcx, rdi; this
0x1800112fc  call    ?Initialize@CDirectMusicSynthPort7@@QEAAJPEAU_DMUS_PORTPARAMS8@@@Z; CDirectMusicSynthPort7::Initialize(_DMUS_PORTPARAMS8 *)
0x180011301  mov     ebx, eax
0x180011303  test    eax, eax
0x180011305  js      short loc_180011321
0x180011307  lea     rcx, [rdi+178h]
0x18001130e  mov     rax, [rbp+arg_20]
0x180011312  mov     [rax], rcx
0x180011315  mov     rax, [rcx]
0x180011318  mov     rax, [rax+8]
0x18001131c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011321  mov     rax, [rdi]
0x180011324  mov     rcx, rdi
0x180011327  mov     rax, [rax+10h]
0x18001132b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011330  mov     rcx, [rbp+var_20]
0x180011334  test    rcx, rcx
0x180011337  jz      short loc_180011345
0x180011339  mov     rax, [rcx]
0x18001133c  mov     rax, [rax+10h]
0x180011340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011345  test    ebx, ebx
0x180011347  js      loc_1800113F0
0x18001134d  test    r14b, r14b
0x180011350  jz      loc_1800113F0
0x180011356  and     dword ptr [rsi+20h], 0FFFFFFFEh
0x18001135a  mov     ebx, 1
0x18001135f  jmp     loc_1800113F0
0x180011364  cmp     [rbp+var_18], 0
0x180011369  jz      loc_1800113F0
0x18001136f  mov     ecx, 368h; Size
0x180011374  call    cs:__imp_malloc
0x18001137a  mov     [rbp+var_10], rax
0x18001137e  test    rax, rax
0x180011381  jz      short loc_18001139A
0x180011383  mov     r9, [rbp+var_18]; struct IDirectMusicSynth8 *
0x180011387  mov     r8, r12; struct CDirectMusic *
0x18001138a  mov     rdx, rdi; struct tagPORTENTRY *
0x18001138d  mov     rcx, rax; this
0x180011390  call    ??0CDirectMusicSynthPort8@@QEAA@PEAUtagPORTENTRY@@PEAVCDirectMusic@@PEAUIDirectMusicSynth8@@@Z; CDirectMusicSynthPort8::CDirectMusicSynthPort8(tagPORTENTRY *,CDirectMusic *,IDirectMusicSynth8 *)
0x180011395  mov     rdi, rax
0x180011398  jmp     short loc_18001139C
0x18001139a  xor     edi, edi
0x18001139c  test    rdi, rdi
0x18001139f  jnz     short loc_1800113A8
0x1800113a1  mov     ebx, 8007000Eh
0x1800113a6  jmp     short loc_1800113DB
0x1800113a8  mov     rdx, rsi; struct _DMUS_PORTPARAMS8 *
0x1800113ab  mov     rcx, rdi; this
0x1800113ae  call    ?Initialize@CDirectMusicSynthPort8@@QEAAJPEAU_DMUS_PORTPARAMS8@@@Z; CDirectMusicSynthPort8::Initialize(_DMUS_PORTPARAMS8 *)
0x1800113b3  mov     ebx, eax
0x1800113b5  test    eax, eax
0x1800113b7  js      short loc_1800113D3
0x1800113b9  lea     rcx, [rdi+178h]
0x1800113c0  mov     rax, [rbp+arg_20]
0x1800113c4  mov     [rax], rcx
0x1800113c7  mov     rax, [rcx]
0x1800113ca  mov     rax, [rax+8]
0x1800113ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113d3  mov     rcx, rdi; this
0x1800113d6  call    ?Release@CDirectMusicSynthPort@@UEAAKXZ; CDirectMusicSynthPort::Release(void)
0x1800113db  mov     rcx, [rbp+var_18]
0x1800113df  test    rcx, rcx
0x1800113e2  jz      short loc_1800113F0
0x1800113e4  mov     rax, [rcx]
0x1800113e7  mov     rax, [rax+10h]
0x1800113eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113f0  mov     eax, ebx
0x1800113f2  add     rsp, 50h
0x1800113f6  pop     r15
0x1800113f8  pop     r14
0x1800113fa  pop     r12
0x1800113fc  pop     rdi
0x1800113fd  pop     rsi
0x1800113fe  pop     rbx
0x1800113ff  pop     rbp
0x180011400  retn
```
