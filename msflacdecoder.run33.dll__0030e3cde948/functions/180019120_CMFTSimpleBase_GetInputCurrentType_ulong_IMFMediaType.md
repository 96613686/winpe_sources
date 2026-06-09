# CMFTSimpleBase::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x180019120`
- end: `0x1800191bf`
- name: `?GetInputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016b74`
- `0x180016f28`
- `0x180019120`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180019160`
- `MFPlat!MFCreateMediaType` at `0x180019160`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetInputCurrentType(CMFTSimpleBase *this, int a2, struct IMFMediaType **a3)
{
  HRESULT v6; // ebx
  char v8; // [rsp+48h] [rbp+20h] BYREF

  CMFTSimpleBase::LockIt::LockIt((CMFTSimpleBase::LockIt *)&v8, this);
  if ( a2 )
  {
    v6 = -1072875853;
  }
  else if ( *((_QWORD *)this + 5) )
  {
    v6 = MFCreateMediaType(a3);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 256LL))(*((_QWORD *)this + 5), *a3);
      if ( v6 < 0 )
      {
        if ( *a3 )
        {
          ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
          *a3 = 0;
        }
      }
    }
  }
  else
  {
    v6 = -1072861856;
  }
  CMFTSimpleBase::LockIt::~LockIt((CMFTSimpleBase::LockIt *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019120  mov     [rsp+arg_0], rbx
0x180019125  mov     [rsp+arg_8], rsi
0x18001912a  push    rdi
0x18001912b  sub     rsp, 20h
0x18001912f  mov     ebx, edx
0x180019131  mov     rsi, rcx
0x180019134  mov     rdx, rcx; struct CMFTSimpleBase *
0x180019137  mov     rdi, r8
0x18001913a  lea     rcx, [rsp+28h+arg_18]; this
0x18001913f  call    ??0LockIt@CMFTSimpleBase@@QEAA@PEAV1@@Z; CMFTSimpleBase::LockIt::LockIt(CMFTSimpleBase *)
0x180019144  test    ebx, ebx
0x180019146  jz      short loc_18001914F
0x180019148  mov     ebx, 0C00D36B3h
0x18001914d  jmp     short loc_1800191A3
0x18001914f  cmp     qword ptr [rsi+28h], 0
0x180019154  jnz     short loc_18001915D
0x180019156  mov     ebx, 0C00D6D60h
0x18001915b  jmp     short loc_1800191A3
0x18001915d  mov     rcx, rdi; ppMFType
0x180019160  call    cs:__imp_MFCreateMediaType
0x180019166  mov     ebx, eax
0x180019168  test    eax, eax
0x18001916a  js      short loc_1800191A3
0x18001916c  mov     rcx, [rsi+28h]
0x180019170  mov     rdx, [rdi]
0x180019173  mov     rax, [rcx]
0x180019176  mov     rax, [rax+100h]
0x18001917d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019182  mov     ebx, eax
0x180019184  test    eax, eax
0x180019186  jns     short loc_1800191A3
0x180019188  mov     rcx, [rdi]
0x18001918b  test    rcx, rcx
0x18001918e  jz      short loc_1800191A3
0x180019190  mov     rax, [rcx]
0x180019193  mov     rax, [rax+10h]
0x180019197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001919c  mov     qword ptr [rdi], 0
0x1800191a3  lea     rcx, [rsp+28h+arg_18]; this
0x1800191a8  call    ??1LockIt@CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::LockIt::~LockIt(void)
0x1800191ad  mov     rsi, [rsp+28h+arg_8]
0x1800191b2  mov     eax, ebx
0x1800191b4  mov     rbx, [rsp+28h+arg_0]
0x1800191b9  add     rsp, 20h
0x1800191bd  pop     rdi
0x1800191be  retn
```
