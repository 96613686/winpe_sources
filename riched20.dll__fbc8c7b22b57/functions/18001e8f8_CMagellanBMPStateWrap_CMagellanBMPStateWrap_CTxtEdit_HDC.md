# CMagellanBMPStateWrap::CMagellanBMPStateWrap(CTxtEdit &,HDC__ *)

- ea: `0x18001e8f8`
- end: `0x18001ead5`
- name: `??0CMagellanBMPStateWrap@@QEAA@AEAVCTxtEdit@@PEAUHDC__@@@Z`
- size: `477`
- prototype: `CMagellanBMPStateWrap *__fastcall(CMagellanBMPStateWrap *__hidden this, struct CTxtEdit *, HDC)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e5e4`
- `0x1800200d0`
- `0x180084910`

## callees

- `0x18001e8f8`
- `0x18003f11c`
- `0x18003ff34`

## import_xrefs

- `GDI32!BitBlt` at `0x18001ea89`
- `GDI32!BitBlt` at `0x18001ea89`
- `GDI32!DeleteDC` at `0x18001eaaf`
- `GDI32!DeleteDC` at `0x18001eaaf`
- `GDI32!CreateCompatibleDC` at `0x18001e99c`
- `GDI32!CreateCompatibleDC` at `0x18001e99c`
- `GDI32!SelectObject` at `0x18001e9bb`
- `GDI32!SelectObject` at `0x18001e9bb`
- `GDI32!DPtoLP` at `0x18001ea1e`
- `GDI32!DPtoLP` at `0x18001ea3c`
- `GDI32!DPtoLP` at `0x18001ea1e`
- `GDI32!DPtoLP` at `0x18001ea3c`
- `GDI32!GetMapMode` at `0x18001e9ca`
- `GDI32!GetMapMode` at `0x18001e9ca`
- `GDI32!SetMapMode` at `0x18001e9db`
- `GDI32!SetMapMode` at `0x18001e9db`
- `GDI32!GetObjectA` at `0x18001e9f4`
- `GDI32!GetObjectA` at `0x18001e9f4`

## pseudocode

```c
CMagellanBMPStateWrap *__fastcall CMagellanBMPStateWrap::CMagellanBMPStateWrap(
        CMagellanBMPStateWrap *this,
        struct CTxtEdit *a2,
        HDC a3)
{
  char *v4; // rbx
  int v5; // esi
  __int16 v6; // r12
  __int64 v8; // r13
  HDC DC; // rax
  HDC v10; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r15
  int MapMode; // eax
  _OWORD pv[2]; // [rsp+50h] [rbp-20h] BYREF
  struct tagPOINT pt; // [rsp+B0h] [rbp+40h] BYREF
  struct tagPOINT x1; // [rsp+B8h] [rbp+48h] BYREF

  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 2) = a2;
  v4 = (char *)a2 + 24;
  v5 = 1;
  if ( !a3 || (*v4 & 1) == 0 )
  {
    v6 = *(_WORD *)v4 & 1;
    if ( (*(_WORD *)v4 & 1) != 0 )
    {
      if ( *((_QWORD *)a2 + 4) )
      {
        v8 = *((_QWORD *)a2 + 8);
        memset(pv, 0, sizeof(pv));
        pt = 0;
        x1 = 0;
        DC = CDevDesc::GetDC((CDevDesc *)(v8 + 16));
        v10 = DC;
        if ( DC )
        {
          CompatibleDC = CreateCompatibleDC(DC);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            SelectObject(CompatibleDC, *((HGDIOBJ *)v4 + 1));
            MapMode = GetMapMode(v10);
            SetMapMode(hdcSrc, MapMode);
            if ( GetObjectA(*((HANDLE *)v4 + 1), 32, pv) )
            {
              pt = *(struct tagPOINT *)((char *)pv + 4);
              DPtoLP(v10, &pt, 1);
              x1 = 0;
              DPtoLP(hdcSrc, &x1, 1);
              BitBlt(
                v10,
                *((_DWORD *)v4 + 4) + ~(pt.x >> 1),
                *((_DWORD *)v4 + 5) - (pt.y >> 1) + 1,
                pt.x,
                pt.y,
                hdcSrc,
                x1.x,
                x1.y,
                0x990066u);
              *(_WORD *)v4 = *(_WORD *)v4 & 0xFFFE | v6 ^ 1;
            }
            DeleteDC(hdcSrc);
          }
          CDevDesc::ReleaseDC((CDevDesc *)(v8 + 16), v10);
        }
      }
      a2 = (struct CTxtEdit *)*((_QWORD *)this + 2);
    }
    else
    {
      v5 = 0;
    }
  }
  *(_DWORD *)this = v5;
  *((_WORD *)a2 + 12) &= ~1u;
  return this;
}

```

## disassembly

```asm
0x18001e8f8  mov     [rsp-38h+arg_10], rbx
0x18001e8fd  push    rbp
0x18001e8fe  push    rsi
0x18001e8ff  push    rdi
0x18001e900  push    r12
0x18001e902  push    r13
0x18001e904  push    r14
0x18001e906  push    r15
0x18001e908  mov     rbp, rsp
0x18001e90b  sub     rsp, 70h
0x18001e90f  xor     r15d, r15d
0x18001e912  mov     [rcx+8], r8
0x18001e916  mov     [rcx+10h], rdx
0x18001e91a  mov     rdi, rcx
0x18001e91d  lea     rbx, [rdx+18h]
0x18001e921  mov     eax, 0FFFEh
0x18001e926  mov     esi, 1
0x18001e92b  test    r8, r8
0x18001e92e  jz      short loc_18001E935
0x18001e930  test    [rbx], sil
0x18001e933  jnz     short loc_18001E941
0x18001e935  movzx   r12d, word ptr [rbx]
0x18001e939  and     r12d, esi
0x18001e93c  jnz     short loc_18001E963
0x18001e93e  mov     esi, r15d
0x18001e941  mov     rbx, [rsp+70h+arg_10]
0x18001e949  mov     [rdi], esi
0x18001e94b  and     [rdx+18h], ax
0x18001e94f  mov     rax, rdi
0x18001e952  add     rsp, 70h
0x18001e956  pop     r15
0x18001e958  pop     r14
0x18001e95a  pop     r13
0x18001e95c  pop     r12
0x18001e95e  pop     rdi
0x18001e95f  pop     rsi
0x18001e960  pop     rbp
0x18001e961  retn
0x18001e963  cmp     [rbx+8], r15
0x18001e967  jz      loc_18001EACC
0x18001e96d  mov     r13, [rdx+40h]
0x18001e971  xorps   xmm0, xmm0
0x18001e974  movups  [rbp+pv], xmm0
0x18001e978  mov     qword ptr [rbp+pt.x], r15
0x18001e97c  movups  [rbp+var_10], xmm0
0x18001e980  lea     rcx, [r13+10h]; this
0x18001e984  mov     qword ptr [rbp+arg_8.x], r15
0x18001e988  call    ?GetDC@CDevDesc@@QEBAPEAUHDC__@@XZ; CDevDesc::GetDC(void)
0x18001e98d  mov     r14, rax
0x18001e990  test    rax, rax
0x18001e993  jz      loc_18001EAC7
0x18001e999  mov     rcx, rax; hdc
0x18001e99c  call    cs:__imp_CreateCompatibleDC
0x18001e9a3  nop     dword ptr [rax+rax+00h]
0x18001e9a8  mov     r15, rax
0x18001e9ab  test    rax, rax
0x18001e9ae  jz      loc_18001EABB
0x18001e9b4  mov     rdx, [rbx+8]; h
0x18001e9b8  mov     rcx, rax; hdc
0x18001e9bb  call    cs:__imp_SelectObject
0x18001e9c2  nop     dword ptr [rax+rax+00h]
0x18001e9c7  mov     rcx, r14; hdc
0x18001e9ca  call    cs:__imp_GetMapMode
0x18001e9d1  nop     dword ptr [rax+rax+00h]
0x18001e9d6  mov     edx, eax; iMode
0x18001e9d8  mov     rcx, r15; hdc
0x18001e9db  call    cs:__imp_SetMapMode
0x18001e9e2  nop     dword ptr [rax+rax+00h]
0x18001e9e7  mov     rcx, [rbx+8]; h
0x18001e9eb  lea     r8, [rbp+pv]; pv
0x18001e9ef  mov     edx, 20h ; ' '; c
0x18001e9f4  call    cs:__imp_GetObjectA
0x18001e9fb  nop     dword ptr [rax+rax+00h]
0x18001ea00  test    eax, eax
0x18001ea02  jz      loc_18001EAAC
0x18001ea08  mov     eax, dword ptr [rbp+pv+4]
0x18001ea0b  lea     rdx, [rbp+pt]; lppt
0x18001ea0f  mov     [rbp+pt.x], eax
0x18001ea12  mov     r8d, esi; c
0x18001ea15  mov     eax, dword ptr [rbp+pv+8]
0x18001ea18  mov     rcx, r14; hdc
0x18001ea1b  mov     [rbp+pt.y], eax
0x18001ea1e  call    cs:__imp_DPtoLP
0x18001ea25  nop     dword ptr [rax+rax+00h]
0x18001ea2a  mov     r8d, esi; c
0x18001ea2d  mov     qword ptr [rbp+arg_8.x], 0
0x18001ea35  lea     rdx, [rbp+arg_8]; lppt
0x18001ea39  mov     rcx, r15; hdc
0x18001ea3c  call    cs:__imp_DPtoLP
0x18001ea43  nop     dword ptr [rax+rax+00h]
0x18001ea48  mov     ecx, [rbp+pt.y]
0x18001ea4b  mov     eax, ecx
0x18001ea4d  mov     r8d, [rbx+14h]
0x18001ea51  mov     r9d, [rbp+pt.x]; cx
0x18001ea55  mov     edx, r9d
0x18001ea58  sar     eax, 1
0x18001ea5a  sub     r8d, eax
0x18001ea5d  mov     [rsp+70h+rop], 990066h; rop
0x18001ea65  mov     eax, [rbp+arg_8.y]
0x18001ea68  add     r8d, esi; y
0x18001ea6b  mov     [rsp+70h+y1], eax; y1
0x18001ea6f  mov     eax, [rbp+arg_8.x]
0x18001ea72  sar     edx, 1
0x18001ea74  mov     [rsp+70h+x1], eax; x1
0x18001ea78  not     edx
0x18001ea7a  add     edx, [rbx+10h]; x
0x18001ea7d  mov     [rsp+70h+hdcSrc], r15; hdcSrc
0x18001ea82  mov     [rsp+70h+cy], ecx; cy
0x18001ea86  mov     rcx, r14; hdc
0x18001ea89  call    cs:__imp_BitBlt
0x18001ea90  nop     dword ptr [rax+rax+00h]
0x18001ea95  movzx   eax, word ptr [rbx]
0x18001ea98  mov     ecx, 0FFFEh
0x18001ea9d  and     ax, cx
0x18001eaa0  xor     r12w, si
0x18001eaa4  or      r12w, ax
0x18001eaa8  mov     [rbx], r12w
0x18001eaac  mov     rcx, r15; hdc
0x18001eaaf  call    cs:__imp_DeleteDC
0x18001eab6  nop     dword ptr [rax+rax+00h]
0x18001eabb  mov     rdx, r14; HDC
0x18001eabe  lea     rcx, [r13+10h]; this
0x18001eac2  call    ?ReleaseDC@CDevDesc@@QEBAXPEAUHDC__@@@Z; CDevDesc::ReleaseDC(HDC__ *)
0x18001eac7  mov     eax, 0FFFEh
0x18001eacc  mov     rdx, [rdi+10h]
0x18001ead0  jmp     loc_18001E941
```
