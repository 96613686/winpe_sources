# CThread::~CThread(void)

- ea: `0x14000799c`
- end: `0x140007a11`
- name: `??1CThread@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CThread *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140007ac0`
- `0x1400080a0`
- `0x14000ac9c`
- `0x14001dc41`

## callees

- `0x140003868`
- `0x140004eb4`
- `0x140007554`
- `0x14000799c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400079ea`
- `KERNEL32!CloseHandle` at `0x1400079f4`
- `KERNEL32!CloseHandle` at `0x1400079ea`
- `KERNEL32!CloseHandle` at `0x1400079f4`

## pseudocode

```c
void __fastcall CThread::~CThread(CThread *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CThread::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    CloseHandle(v2);
  CloseHandle(*((HANDLE *)this + 4));
  _bstr_t::_Free((CThread *)((char *)this + 40));
  R<IObjectContext>::~R<IObjectContext>((__int64 *)this + 2);
}

```

## disassembly

```asm
0x14000799c  push    rbx
0x14000799e  sub     rsp, 20h
0x1400079a2  mov     rbx, rcx
0x1400079a5  lea     rax, ??_7CThread@@6B@; const CThread::`vftable'
0x1400079ac  mov     [rcx], rax
0x1400079af  lea     rax, WPP_GLOBAL_Control
0x1400079b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079bd  cmp     rcx, rax
0x1400079c0  jz      short loc_1400079E1
0x1400079c2  test    byte ptr [rcx+1Ch], 4
0x1400079c6  jz      short loc_1400079E1
0x1400079c8  mov     edx, 0Ch
0x1400079cd  mov     r9d, [rbx+18h]
0x1400079d1  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x1400079d8  mov     rcx, [rcx+10h]
0x1400079dc  call    WPP_SF_d
0x1400079e1  mov     rcx, [rbx+50h]; hObject
0x1400079e5  test    rcx, rcx
0x1400079e8  jz      short loc_1400079F0
0x1400079ea  call    cs:__imp_CloseHandle
0x1400079f0  mov     rcx, [rbx+20h]; hObject
0x1400079f4  call    cs:__imp_CloseHandle
0x1400079fa  lea     rcx, [rbx+28h]; this
0x1400079fe  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140007a03  lea     rcx, [rbx+10h]
0x140007a07  add     rsp, 20h
0x140007a0b  pop     rbx
0x140007a0c  jmp     ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
```
