# CApiPortClient::SendRequest(void const *,short,long *,void *,short)

- ea: `0x18000925c`
- end: `0x1800092b2`
- name: `?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z`
- size: `86`
- prototype: `__int64 __fastcall(CApiPortClient *__hidden this, const void *, __int16, int *, void *, __int16)`
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a8e0`
- `0x1800111c0`
- `0x180011240`
- `0x1800112c0`
- `0x180011340`
- `0x180011410`
- `0x1800114e0`
- `0x1800115c0`
- `0x180011650`
- `0x1800124d0`
- `0x180012550`
- `0x1800125d0`
- `0x180012650`
- `0x1800126d0`
- `0x180012750`
- `0x180012870`
- `0x180012aa0`
- `0x180012de0`
- `0x180012e60`
- `0x180012ee0`
- `0x180012f60`
- `0x180013010`
- `0x1800130c0`
- `0x180013140`
- `0x1800131c0`
- `0x180013910`
- `0x180014ce0`

## callees

- `0x18000af44`
- `0x18000bab0`

## pseudocode

```c
__int64 __fastcall CApiPortClient::SendRequest(
        CApiPortClient *this,
        unsigned int *a2,
        __int16 a3,
        int *a4,
        void *a5,
        __int16 a6)
{
  unsigned int v6; // ebx
  void **v8; // [rsp+40h] [rbp-28h] BYREF
  __int128 v9; // [rsp+48h] [rbp-20h] BYREF

  v8 = &CStandardData::`vftable';
  v9 = 0;
  v6 = CApiPortClient::SendRequest(this, a2, a3, (const struct CAlpcView **)&v8, a4, a5, a6);
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((_QWORD *)&v9 + 1);
  return v6;
}

```

## disassembly

```asm
0x18000925c  mov     r11, rsp
0x18000925f  push    rbx
0x180009260  sub     rsp, 60h
0x180009264  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x18000926b  xorps   xmm0, xmm0
0x18000926e  mov     [r11-28h], rax
0x180009272  movzx   eax, [rsp+68h+arg_28]
0x18000927a  mov     [rsp+68h+var_38], ax; __int16
0x18000927f  mov     rax, [rsp+68h+arg_20]
0x180009287  mov     [r11-40h], rax
0x18000928b  mov     [r11-48h], r9
0x18000928f  lea     r9, [r11-28h]; struct CStandardData *
0x180009293  movdqu  [rsp+68h+var_20], xmm0
0x180009299  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFAEBVCStandardData@@PEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,CStandardData const &,long *,void *,short)
0x18000929e  lea     rcx, [rsp+68h+var_20+8]
0x1800092a3  mov     ebx, eax
0x1800092a5  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x1800092aa  mov     eax, ebx
0x1800092ac  add     rsp, 60h
0x1800092b0  pop     rbx
0x1800092b1  retn
```
