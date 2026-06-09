# CMsftDiscRecorder2::GetAdapterDescriptor(uchar * *,ulong *)

- ea: `0x180029680`
- end: `0x180029836`
- name: `?GetAdapterDescriptor@CMsftDiscRecorder2@@UEAAJPEAPEAEPEAK@Z`
- size: `438`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180014134`
- `0x180016778`
- `0x180029680`
- `0x180049832`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002972b`
- `ole32!CoTaskMemFree` at `0x18002972b`
- `ole32!CoTaskMemAlloc` at `0x1800297a4`
- `ole32!CoTaskMemAlloc` at `0x1800297a4`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetAdapterDescriptor(
        CMsftDiscRecorder2 *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  PVOID *v6; // rcx
  int v7; // ebx
  __int64 v9; // r9
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rsi

  if ( a2 )
  {
    v7 = 0;
    *a2 = 0;
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 77, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = -2147467261;
  }
  if ( a3 )
  {
    *a3 = 0;
    if ( v7 >= 0 )
    {
      v9 = *((unsigned int *)this + 58);
      if ( (v9 & 2) != 0 )
      {
        v10 = (unsigned __int8 *)CoTaskMemAlloc(*(unsigned int *)(*((_QWORD *)this + 17) + 4LL));
        v11 = v10;
        if ( v10 )
        {
          v7 = 0;
          memcpy_0(v10, *((const void **)this + 17), *(unsigned int *)(*((_QWORD *)this + 17) + 4LL));
          *a2 = v11;
          *a3 = *(_DWORD *)(*((_QWORD *)this + 17) + 4LL);
          return (unsigned int)v7;
        }
        v7 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            80,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            *(unsigned int *)(*((_QWORD *)this + 17) + 4LL),
            *(_DWORD *)(*((_QWORD *)this + 17) + 4LL));
        }
      }
      else
      {
        v7 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            79,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            v9,
            -2147467259);
        }
      }
    }
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 4) != 0 && *((_BYTE *)v6 + 185) >= 3u )
      WPP_SF_(v6[22], 78, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v7 = -2147467261;
  }
  CoTaskMemFree(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029680  push    rbx
0x180029682  push    rsi
0x180029683  push    rdi
0x180029684  push    r13
0x180029686  push    r14
0x180029688  push    r15
0x18002968a  sub     rsp, 38h
0x18002968e  lea     r13, WPP_GLOBAL_Control
0x180029695  mov     r14, r8
0x180029698  mov     r15, rdx
0x18002969b  mov     rdi, rcx
0x18002969e  mov     esi, 80004003h
0x1800296a3  test    rdx, rdx
0x1800296a6  jnz     short loc_1800296E8
0x1800296a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296af  cmp     rcx, r13
0x1800296b2  jz      short loc_1800296E4
0x1800296b4  test    byte ptr [rcx+0BCh], 4
0x1800296bb  jz      short loc_1800296E4
0x1800296bd  cmp     byte ptr [rcx+0B9h], 3
0x1800296c4  jb      short loc_1800296E4
0x1800296c6  mov     rcx, [rcx+0B0h]
0x1800296cd  lea     edx, [r15+4Dh]
0x1800296d1  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800296d8  call    WPP_SF_
0x1800296dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296e4  mov     ebx, esi
0x1800296e6  jmp     short loc_1800296F4
0x1800296e8  xor     ebx, ebx
0x1800296ea  mov     [rdx], rbx
0x1800296ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296f4  test    r14, r14
0x1800296f7  jnz     short loc_180029741
0x1800296f9  cmp     rcx, r13
0x1800296fc  jz      short loc_180029727
0x1800296fe  test    byte ptr [rcx+0BCh], 4
0x180029705  jz      short loc_180029727
0x180029707  cmp     byte ptr [rcx+0B9h], 3
0x18002970e  jb      short loc_180029727
0x180029710  mov     rcx, [rcx+0B0h]
0x180029717  lea     edx, [r14+4Eh]
0x18002971b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029722  call    WPP_SF_
0x180029727  mov     ebx, esi
0x180029729  xor     ecx, ecx; pv
0x18002972b  call    cs:__imp_CoTaskMemFree
0x180029731  mov     eax, ebx
0x180029733  add     rsp, 38h
0x180029737  pop     r15
0x180029739  pop     r14
0x18002973b  pop     r13
0x18002973d  pop     rdi
0x18002973e  pop     rsi
0x18002973f  pop     rbx
0x180029740  retn
0x180029741  mov     dword ptr [r14], 0
0x180029748  test    ebx, ebx
0x18002974a  js      short loc_180029729
0x18002974c  mov     r9d, [rdi+0E8h]
0x180029753  test    r9b, 2
0x180029757  jnz     short loc_18002979A
0x180029759  mov     ebx, 80004005h
0x18002975e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029765  cmp     rcx, r13
0x180029768  jz      short loc_180029729
0x18002976a  test    byte ptr [rcx+0BCh], 4
0x180029771  jz      short loc_180029729
0x180029773  cmp     byte ptr [rcx+0B9h], 3
0x18002977a  jb      short loc_180029729
0x18002977c  mov     rcx, [rcx+0B0h]
0x180029783  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002978a  mov     edx, 4Fh ; 'O'
0x18002978f  mov     [rsp+68h+var_48], ebx
0x180029793  call    WPP_SF_Dd
0x180029798  jmp     short loc_180029729
0x18002979a  mov     rax, [rdi+88h]
0x1800297a1  mov     ecx, [rax+4]; cb
0x1800297a4  call    cs:__imp_CoTaskMemAlloc
0x1800297aa  mov     rsi, rax
0x1800297ad  test    rax, rax
0x1800297b0  jnz     short loc_18002980C
0x1800297b2  mov     ebx, 8007000Eh
0x1800297b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297be  cmp     rcx, r13
0x1800297c1  jz      loc_180029729
0x1800297c7  test    byte ptr [rcx+0BCh], 4
0x1800297ce  jz      loc_180029729
0x1800297d4  cmp     byte ptr [rcx+0B9h], 3
0x1800297db  jb      loc_180029729
0x1800297e1  mov     rax, [rdi+88h]
0x1800297e8  lea     edx, [rsi+50h]
0x1800297eb  mov     rcx, [rcx+0B0h]
0x1800297f2  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800297f9  mov     r9d, [rax+4]
0x1800297fd  mov     [rsp+68h+var_48], r9d
0x180029802  call    WPP_SF_Dd
0x180029807  jmp     loc_180029729
0x18002980c  mov     rdx, [rdi+88h]; Src
0x180029813  xor     ebx, ebx
0x180029815  mov     rcx, rsi; void *
0x180029818  mov     r8d, [rdx+4]; Size
0x18002981c  call    memcpy_0
0x180029821  mov     [r15], rsi
0x180029824  mov     rax, [rdi+88h]
0x18002982b  mov     ecx, [rax+4]
0x18002982e  mov     [r14], ecx
0x180029831  jmp     loc_180029731
```
