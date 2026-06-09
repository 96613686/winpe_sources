# CMFTSimpleBase::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800193d0`
- end: `0x18001946f`
- name: `?GetOutputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016b74`
- `0x180016f28`
- `0x1800193d0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180019410`
- `MFPlat!MFCreateMediaType` at `0x180019410`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetOutputCurrentType(CMFTSimpleBase *this, int a2, struct IMFMediaType **a3)
{
  HRESULT v6; // ebx
  char v8; // [rsp+48h] [rbp+20h] BYREF

  CMFTSimpleBase::LockIt::LockIt((CMFTSimpleBase::LockIt *)&v8, this);
  if ( a2 )
  {
    v6 = -1072875853;
  }
  else if ( *((_QWORD *)this + 10) )
  {
    v6 = MFCreateMediaType(a3);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 256LL))(*((_QWORD *)this + 10), *a3);
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
0x1800193d0  mov     [rsp+arg_0], rbx
0x1800193d5  mov     [rsp+arg_8], rsi
0x1800193da  push    rdi
0x1800193db  sub     rsp, 20h
0x1800193df  mov     ebx, edx
0x1800193e1  mov     rsi, rcx
0x1800193e4  mov     rdx, rcx; struct CMFTSimpleBase *
0x1800193e7  mov     rdi, r8
0x1800193ea  lea     rcx, [rsp+28h+arg_18]; this
0x1800193ef  call    ??0LockIt@CMFTSimpleBase@@QEAA@PEAV1@@Z; CMFTSimpleBase::LockIt::LockIt(CMFTSimpleBase *)
0x1800193f4  test    ebx, ebx
0x1800193f6  jz      short loc_1800193FF
0x1800193f8  mov     ebx, 0C00D36B3h
0x1800193fd  jmp     short loc_180019453
0x1800193ff  cmp     qword ptr [rsi+50h], 0
0x180019404  jnz     short loc_18001940D
0x180019406  mov     ebx, 0C00D6D60h
0x18001940b  jmp     short loc_180019453
0x18001940d  mov     rcx, rdi; ppMFType
0x180019410  call    cs:__imp_MFCreateMediaType
0x180019416  mov     ebx, eax
0x180019418  test    eax, eax
0x18001941a  js      short loc_180019453
0x18001941c  mov     rcx, [rsi+50h]
0x180019420  mov     rdx, [rdi]
0x180019423  mov     rax, [rcx]
0x180019426  mov     rax, [rax+100h]
0x18001942d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019432  mov     ebx, eax
0x180019434  test    eax, eax
0x180019436  jns     short loc_180019453
0x180019438  mov     rcx, [rdi]
0x18001943b  test    rcx, rcx
0x18001943e  jz      short loc_180019453
0x180019440  mov     rax, [rcx]
0x180019443  mov     rax, [rax+10h]
0x180019447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001944c  mov     qword ptr [rdi], 0
0x180019453  lea     rcx, [rsp+28h+arg_18]; this
0x180019458  call    ??1LockIt@CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::LockIt::~LockIt(void)
0x18001945d  mov     rsi, [rsp+28h+arg_8]
0x180019462  mov     eax, ebx
0x180019464  mov     rbx, [rsp+28h+arg_0]
0x180019469  add     rsp, 20h
0x18001946d  pop     rdi
0x18001946e  retn
```
