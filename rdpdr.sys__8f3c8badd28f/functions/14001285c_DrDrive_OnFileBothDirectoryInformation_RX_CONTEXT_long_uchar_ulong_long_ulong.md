# DrDrive::OnFileBothDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)

- ea: `0x14001285c`
- end: `0x140012a33`
- name: `?OnFileBothDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z`
- size: `471`
- prototype: `__int64 __fastcall(DrDrive *__hidden this, struct _RX_CONTEXT *, int, unsigned __int8 *, unsigned int, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400131e0`
- `0x1400152a0`

## callees

- `0x14000324c`
- `0x1400065c0`
- `0x14001285c`

## pseudocode

```c
__int64 __fastcall DrDrive::OnFileBothDirectoryInformation(
        DrDrive *this,
        struct _RX_CONTEXT *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int *a6,
        unsigned int *a7)
{
  PDFS_NAME_CONTEXT DfsNameContext; // rbx
  unsigned int v10; // ecx
  __int64 result; // rax
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // edx

  if ( a3 < 0 )
  {
    *a6 = a3;
    goto LABEL_25;
  }
  if ( a5 >= 0x5D )
  {
    if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) < 0x5Eu )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_18;
      v15 = 39;
    }
    else
    {
      DfsNameContext = a2->Create.NtCreateParameters.DfsNameContext;
      *((_QWORD *)DfsNameContext + 6) = *((_QWORD *)a4 + 6);
      *((_QWORD *)DfsNameContext + 4) = *((_QWORD *)a4 + 4);
      *((_QWORD *)DfsNameContext + 1) = *((_QWORD *)a4 + 1);
      *((_DWORD *)DfsNameContext + 16) = *((_DWORD *)a4 + 16);
      *((_QWORD *)DfsNameContext + 5) = *((_QWORD *)a4 + 5);
      *((_DWORD *)DfsNameContext + 14) = *((_DWORD *)a4 + 14);
      *((_DWORD *)DfsNameContext + 1) = *((_DWORD *)a4 + 1);
      *((_DWORD *)DfsNameContext + 15) = *((_DWORD *)a4 + 15);
      *((_QWORD *)DfsNameContext + 2) = *((_QWORD *)a4 + 2);
      *((_QWORD *)DfsNameContext + 3) = *((_QWORD *)a4 + 3);
      *(_DWORD *)DfsNameContext = *(_DWORD *)a4;
      *((_BYTE *)DfsNameContext + 68) = a4[68];
      *(_OWORD *)((char *)DfsNameContext + 70) = *(_OWORD *)(a4 + 69);
      *(_QWORD *)((char *)DfsNameContext + 86) = *(_QWORD *)(a4 + 85);
      *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 94;
      v10 = *((_DWORD *)DfsNameContext + 15);
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) >= v10 )
      {
        if ( a5 == v10 + 93 && *((_BYTE *)DfsNameContext + 68) <= 0x18u )
        {
          memmove((char *)DfsNameContext + 94, a4 + 93, v10);
          *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= *((_DWORD *)DfsNameContext + 15);
          *a6 = a3;
          *a7 = a5;
          return 0;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_23;
        v13 = 37;
        goto LABEL_22;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_18;
      v15 = 38;
    }
    WPP_SF_(v14->AttachedDevice, v15, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_18:
    *a6 = -2147483643;
LABEL_25:
    v16 = 0;
    goto LABEL_26;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    goto LABEL_23;
  v13 = 40;
LABEL_22:
  WPP_SF_(v12->AttachedDevice, v13, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_23:
  v16 = -1073741434;
  *a6 = -1073741434;
LABEL_26:
  result = v16;
  *a7 = 0;
  return result;
}

```

## disassembly

```asm
0x14001285c  push    rbx
0x14001285e  push    rbp
0x14001285f  push    rsi
0x140012860  push    rdi
0x140012861  sub     rsp, 28h
0x140012865  mov     ebp, r8d
0x140012868  mov     rdi, rdx
0x14001286b  test    r8d, r8d
0x14001286e  js      loc_140012A10
0x140012874  mov     esi, [rsp+48h+arg_20]
0x140012878  cmp     esi, 5Dh ; ']'
0x14001287b  jb      loc_1400129D4
0x140012881  cmp     dword ptr [rdx+1D8h], 5Eh ; '^'
0x140012888  jb      loc_140012999
0x14001288e  mov     rbx, [rdx+1C8h]
0x140012895  mov     rax, [r9+30h]
0x140012899  mov     [rbx+30h], rax
0x14001289d  mov     rax, [r9+20h]
0x1400128a1  mov     [rbx+20h], rax
0x1400128a5  mov     rax, [r9+8]
0x1400128a9  mov     [rbx+8], rax
0x1400128ad  mov     eax, [r9+40h]
0x1400128b1  mov     [rbx+40h], eax
0x1400128b4  mov     rax, [r9+28h]
0x1400128b8  mov     [rbx+28h], rax
0x1400128bc  mov     eax, [r9+38h]
0x1400128c0  mov     [rbx+38h], eax
0x1400128c3  mov     eax, [r9+4]
0x1400128c7  mov     [rbx+4], eax
0x1400128ca  mov     eax, [r9+3Ch]
0x1400128ce  mov     [rbx+3Ch], eax
0x1400128d1  mov     rax, [r9+10h]
0x1400128d5  mov     [rbx+10h], rax
0x1400128d9  mov     rax, [r9+18h]
0x1400128dd  mov     [rbx+18h], rax
0x1400128e1  mov     eax, [r9]
0x1400128e4  mov     [rbx], eax
0x1400128e6  mov     al, [r9+44h]
0x1400128ea  mov     [rbx+44h], al
0x1400128ed  movups  xmm0, xmmword ptr [r9+45h]
0x1400128f2  movups  xmmword ptr [rbx+46h], xmm0
0x1400128f6  movsd   xmm1, qword ptr [r9+55h]
0x1400128fc  movsd   qword ptr [rbx+56h], xmm1
0x140012901  add     dword ptr [rdx+1D8h], 0FFFFFFA2h
0x140012908  mov     ecx, [rbx+3Ch]
0x14001290b  cmp     [rdx+1D8h], ecx
0x140012911  jb      short loc_140012979
0x140012913  lea     eax, [rcx+5Dh]
0x140012916  cmp     esi, eax
0x140012918  jnz     short loc_140012951
0x14001291a  cmp     byte ptr [rbx+44h], 18h
0x14001291e  ja      short loc_140012951
0x140012920  mov     r8d, ecx; Size
0x140012923  lea     rdx, [r9+5Dh]; Src
0x140012927  lea     rcx, [rbx+5Eh]; void *
0x14001292b  call    memmove
0x140012930  mov     eax, [rbx+3Ch]
0x140012933  sub     [rdi+1D8h], eax
0x140012939  mov     rax, [rsp+48h+arg_28]
0x14001293e  mov     [rax], ebp
0x140012940  mov     rax, [rsp+48h+arg_30]
0x140012948  mov     [rax], esi
0x14001294a  xor     eax, eax
0x14001294c  jmp     loc_140012A29
0x140012951  mov     rcx, cs:WPP_GLOBAL_Control
0x140012958  lea     rax, WPP_GLOBAL_Control
0x14001295f  cmp     rcx, rax
0x140012962  jz      loc_140012A02
0x140012968  cmp     byte ptr [rcx+29h], 2
0x14001296c  jb      loc_140012A02
0x140012972  mov     edx, 25h ; '%'
0x140012977  jmp     short loc_1400129F2
0x140012979  mov     rcx, cs:WPP_GLOBAL_Control
0x140012980  lea     rax, WPP_GLOBAL_Control
0x140012987  cmp     rcx, rax
0x14001298a  jz      short loc_1400129C7
0x14001298c  cmp     byte ptr [rcx+29h], 2
0x140012990  jb      short loc_1400129C7
0x140012992  mov     edx, 26h ; '&'
0x140012997  jmp     short loc_1400129B7
0x140012999  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129a0  lea     rax, WPP_GLOBAL_Control
0x1400129a7  cmp     rcx, rax
0x1400129aa  jz      short loc_1400129C7
0x1400129ac  cmp     byte ptr [rcx+29h], 2
0x1400129b0  jb      short loc_1400129C7
0x1400129b2  mov     edx, 27h ; '''
0x1400129b7  mov     rcx, [rcx+18h]
0x1400129bb  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400129c2  call    WPP_SF_
0x1400129c7  mov     rax, [rsp+48h+arg_28]
0x1400129cc  mov     dword ptr [rax], 80000005h
0x1400129d2  jmp     short loc_140012A17
0x1400129d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129db  lea     rax, WPP_GLOBAL_Control
0x1400129e2  cmp     rcx, rax
0x1400129e5  jz      short loc_140012A02
0x1400129e7  cmp     byte ptr [rcx+29h], 2
0x1400129eb  jb      short loc_140012A02
0x1400129ed  mov     edx, 28h ; '('
0x1400129f2  mov     rcx, [rcx+18h]
0x1400129f6  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400129fd  call    WPP_SF_
0x140012a02  mov     rax, [rsp+48h+arg_28]
0x140012a07  mov     edx, 0C0000186h
0x140012a0c  mov     [rax], edx
0x140012a0e  jmp     short loc_140012A19
0x140012a10  mov     rax, [rsp+48h+arg_28]
0x140012a15  mov     [rax], ebp
0x140012a17  xor     edx, edx
0x140012a19  mov     rcx, [rsp+48h+arg_30]
0x140012a21  mov     eax, edx
0x140012a23  mov     dword ptr [rcx], 0
0x140012a29  add     rsp, 28h
0x140012a2d  pop     rdi
0x140012a2e  pop     rsi
0x140012a2f  pop     rbp
0x140012a30  pop     rbx
0x140012a31  retn
```
