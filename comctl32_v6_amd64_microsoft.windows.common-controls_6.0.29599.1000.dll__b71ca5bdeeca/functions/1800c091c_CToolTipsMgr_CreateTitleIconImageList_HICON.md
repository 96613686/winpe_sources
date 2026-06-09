# CToolTipsMgr::CreateTitleIconImageList(HICON__ *)

- ea: `0x1800c091c`
- end: `0x1800c0b3c`
- name: `?CreateTitleIconImageList@CToolTipsMgr@@AEAAHPEAUHICON__@@@Z`
- size: `544`
- prototype: `int(CToolTipsMgr *__hidden this, HICON)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800c0854`

## callees

- `0x180019b30`
- `0x18003bbd0`
- `0x1800b68d0`
- `0x1800c091c`
- `0x180114520`
- `0x1801328cc`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800c0a9d`
- `GDI32!DeleteObject` at `0x1800c0aa7`
- `GDI32!DeleteObject` at `0x1800c0a9d`
- `GDI32!DeleteObject` at `0x1800c0aa7`
- `GDI32!GetObjectW` at `0x1800c0a7e`
- `GDI32!GetObjectW` at `0x1800c0a7e`
- `USER32!GetIconInfo` at `0x1800c09bd`
- `USER32!GetIconInfo` at `0x1800c09bd`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0952`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0963`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0974`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0985`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0952`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0963`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0974`
- `USER32!GetSystemMetricsForDpi` at `0x1800c0985`

## pseudocode

```c
__int64 __fastcall CToolTipsMgr::CreateTitleIconImageList(CToolTipsMgr *this, HICON a2)
{
  int SystemMetricsForDpi; // r15d
  int v5; // r12d
  int v6; // r13d
  unsigned int v7; // ebx
  BOOL v8; // edi
  HIMAGELIST *v9; // rdi
  int v10; // eax
  struct _IMAGELIST *v11; // rcx
  int v13; // r8d
  int v14; // edx
  int v15; // [rsp+20h] [rbp-60h]
  ICONINFO piconinfo; // [rsp+28h] [rbp-58h] BYREF
  int v17; // [rsp+48h] [rbp-38h] BYREF
  int cy; // [rsp+4Ch] [rbp-34h] BYREF
  _OWORD pv[2]; // [rsp+50h] [rbp-30h] BYREF

  SystemMetricsForDpi = GetSystemMetricsForDpi(11, *((unsigned int *)this + 15));
  v5 = GetSystemMetricsForDpi(12, *((unsigned int *)this + 16));
  v6 = GetSystemMetricsForDpi(49, *((unsigned int *)this + 15));
  v7 = 0;
  v15 = GetSystemMetricsForDpi(50, *((unsigned int *)this + 16));
  v8 = 0;
  if ( (unsigned __int64)a2 <= 6 )
  {
    LOBYTE(v8) = (unsigned __int64)a2 > 3;
  }
  else
  {
    piconinfo.fIcon = 1;
    memset(&piconinfo.xHotspot, 0, 28);
    memset(pv, 0, sizeof(pv));
    if ( GetIconInfo(a2, &piconinfo) )
    {
      if ( GetObjectW(piconinfo.hbmColor, 32, pv) && SDWORD1(pv[0]) >= SystemMetricsForDpi )
        v8 = SDWORD2(pv[0]) >= v5;
      DeleteObject(piconinfo.hbmColor);
      DeleteObject(piconinfo.hbmMask);
    }
  }
  v17 = 0;
  cy = 0;
  if ( !v8 )
  {
    v9 = (HIMAGELIST *)((char *)this + 176);
    if ( *((_QWORD *)this + 22) && ImageList_GetIconSize(*v9, &v17, &cy) )
    {
      if ( v17 == v6 )
      {
        v10 = v15;
        if ( cy == v15 )
          goto LABEL_8;
      }
      ImageList_DestroyPrivate(*v9, 0);
      *v9 = 0;
    }
    v10 = v15;
LABEL_8:
    if ( *v9 )
      goto LABEL_9;
    v13 = v10;
    v14 = v6;
LABEL_26:
    CreateImageListHelper(v9, v14, v13);
    goto LABEL_9;
  }
  v9 = (HIMAGELIST *)((char *)this + 184);
  if ( !*((_QWORD *)this + 23) )
    goto LABEL_23;
  if ( ImageList_GetIconSize(*v9, &v17, &cy) && (v17 != SystemMetricsForDpi || cy != v5) )
  {
    ImageList_DestroyPrivate(*v9, 0);
    *v9 = 0;
  }
  if ( !*v9 )
  {
LABEL_23:
    v13 = v5;
    v14 = SystemMetricsForDpi;
    goto LABEL_26;
  }
LABEL_9:
  v11 = *v9;
  *((_QWORD *)this + 24) = *v9;
  if ( (unsigned __int64)a2 > 6 && v11 )
    ImageList_ReplaceIcon(v11, 3, a2);
  LOBYTE(v7) = *((_QWORD *)this + 24) != 0;
  return v7;
}

```

## disassembly

```asm
0x1800c091c  mov     [rsp-38h+arg_10], rbx
0x1800c0921  push    rbp
0x1800c0922  push    rsi
0x1800c0923  push    rdi
0x1800c0924  push    r12
0x1800c0926  push    r13
0x1800c0928  push    r14
0x1800c092a  push    r15
0x1800c092c  mov     rbp, rsp
0x1800c092f  sub     rsp, 80h
0x1800c0936  mov     rax, cs:__security_cookie
0x1800c093d  xor     rax, rsp
0x1800c0940  mov     [rbp+var_10], rax
0x1800c0944  mov     r14, rdx
0x1800c0947  mov     rsi, rcx
0x1800c094a  mov     edx, [rcx+3Ch]
0x1800c094d  mov     ecx, 0Bh
0x1800c0952  call    cs:__imp_GetSystemMetricsForDpi
0x1800c0958  mov     edx, [rsi+40h]
0x1800c095b  mov     ecx, 0Ch
0x1800c0960  mov     r15d, eax
0x1800c0963  call    cs:__imp_GetSystemMetricsForDpi
0x1800c0969  mov     edx, [rsi+3Ch]
0x1800c096c  mov     ecx, 31h ; '1'
0x1800c0971  mov     r12d, eax
0x1800c0974  call    cs:__imp_GetSystemMetricsForDpi
0x1800c097a  mov     edx, [rsi+40h]
0x1800c097d  mov     ecx, 32h ; '2'
0x1800c0982  mov     r13d, eax
0x1800c0985  call    cs:__imp_GetSystemMetricsForDpi
0x1800c098b  xor     ebx, ebx
0x1800c098d  mov     [rbp+var_60], eax
0x1800c0990  mov     edi, ebx
0x1800c0992  cmp     r14, 6
0x1800c0996  jbe     loc_1800C0A64
0x1800c099c  xorps   xmm0, xmm0
0x1800c099f  mov     [rbp+piconinfo.fIcon], 1
0x1800c09a6  movups  xmmword ptr [rbp+piconinfo.xHotspot], xmm0
0x1800c09aa  lea     rdx, [rbp+piconinfo]; piconinfo
0x1800c09ae  mov     rcx, r14; hIcon
0x1800c09b1  movups  xmmword ptr [rbp+piconinfo.hbmMask], xmm0
0x1800c09b5  movups  [rbp+pv], xmm0
0x1800c09b9  movups  [rbp+var_20], xmm0
0x1800c09bd  call    cs:__imp_GetIconInfo
0x1800c09c3  test    eax, eax
0x1800c09c5  jnz     loc_1800C0A71
0x1800c09cb  mov     [rbp+var_38], ebx
0x1800c09ce  mov     [rbp+cy], ebx
0x1800c09d1  test    edi, edi
0x1800c09d3  jnz     loc_1800C0AB2
0x1800c09d9  lea     rdi, [rsi+0B0h]
0x1800c09e0  cmp     [rdi], rbx
0x1800c09e3  jz      short loc_1800C0A5F
0x1800c09e5  mov     rcx, [rdi]; himl
0x1800c09e8  lea     r8, [rbp+cy]; cy
0x1800c09ec  lea     rdx, [rbp+var_38]; cx
0x1800c09f0  call    ImageList_GetIconSize
0x1800c09f5  test    eax, eax
0x1800c09f7  jz      short loc_1800C0A5F
0x1800c09f9  cmp     [rbp+var_38], r13d
0x1800c09fd  jnz     loc_1800C0AFC
0x1800c0a03  mov     eax, [rbp+var_60]
0x1800c0a06  cmp     [rbp+cy], eax
0x1800c0a09  jnz     loc_1800C0AFC
0x1800c0a0f  cmp     [rdi], rbx
0x1800c0a12  jz      loc_1800C0B0E
0x1800c0a18  mov     rcx, [rdi]; himl
0x1800c0a1b  mov     [rsi+0C0h], rcx
0x1800c0a22  cmp     r14, 6
0x1800c0a26  ja      loc_1800C0B21
0x1800c0a2c  cmp     [rsi+0C0h], rbx
0x1800c0a33  setnz   bl
0x1800c0a36  mov     eax, ebx
0x1800c0a38  mov     rcx, [rbp+var_10]
0x1800c0a3c  xor     rcx, rsp; StackCookie
0x1800c0a3f  call    __security_check_cookie
0x1800c0a44  mov     rbx, [rsp+80h+arg_10]
0x1800c0a4c  add     rsp, 80h
0x1800c0a53  pop     r15
0x1800c0a55  pop     r14
0x1800c0a57  pop     r13
0x1800c0a59  pop     r12
0x1800c0a5b  pop     rdi
0x1800c0a5c  pop     rsi
0x1800c0a5d  pop     rbp
0x1800c0a5e  retn
0x1800c0a5f  mov     eax, [rbp+var_60]
0x1800c0a62  jmp     short loc_1800C0A0F
0x1800c0a64  cmp     r14, 3
0x1800c0a68  setnbe  dil
0x1800c0a6c  jmp     loc_1800C09CB
0x1800c0a71  mov     rcx, [rbp+piconinfo.hbmColor]; h
0x1800c0a75  lea     r8, [rbp+pv]; pv
0x1800c0a79  mov     edx, 20h ; ' '; c
0x1800c0a7e  call    cs:__imp_GetObjectW
0x1800c0a84  test    eax, eax
0x1800c0a86  jz      short loc_1800C0A99
0x1800c0a88  cmp     dword ptr [rbp+pv+4], r15d
0x1800c0a8c  jl      short loc_1800C0A99
0x1800c0a8e  cmp     dword ptr [rbp+pv+8], r12d
0x1800c0a92  jl      short loc_1800C0A99
0x1800c0a94  mov     edi, 1
0x1800c0a99  mov     rcx, [rbp+piconinfo.hbmColor]; ho
0x1800c0a9d  call    cs:__imp_DeleteObject
0x1800c0aa3  mov     rcx, [rbp+piconinfo.hbmMask]; ho
0x1800c0aa7  call    cs:__imp_DeleteObject
0x1800c0aad  jmp     loc_1800C09CB
0x1800c0ab2  lea     rdi, [rsi+0B8h]
0x1800c0ab9  cmp     [rdi], rbx
0x1800c0abc  jz      short loc_1800C0AF4
0x1800c0abe  mov     rcx, [rdi]; himl
0x1800c0ac1  lea     r8, [rbp+cy]; cy
0x1800c0ac5  lea     rdx, [rbp+var_38]; cx
0x1800c0ac9  call    ImageList_GetIconSize
0x1800c0ace  test    eax, eax
0x1800c0ad0  jz      short loc_1800C0AEB
0x1800c0ad2  cmp     [rbp+var_38], r15d
0x1800c0ad6  jnz     short loc_1800C0ADE
0x1800c0ad8  cmp     [rbp+cy], r12d
0x1800c0adc  jz      short loc_1800C0AEB
0x1800c0ade  mov     rcx, [rdi]
0x1800c0ae1  xor     edx, edx
0x1800c0ae3  call    ImageList_DestroyPrivate
0x1800c0ae8  mov     [rdi], rbx
0x1800c0aeb  cmp     [rdi], rbx
0x1800c0aee  jnz     loc_1800C0A18
0x1800c0af4  mov     r8d, r12d
0x1800c0af7  mov     edx, r15d
0x1800c0afa  jmp     short loc_1800C0B14
0x1800c0afc  mov     rcx, [rdi]
0x1800c0aff  xor     edx, edx
0x1800c0b01  call    ImageList_DestroyPrivate
0x1800c0b06  mov     [rdi], rbx
0x1800c0b09  jmp     loc_1800C0A5F
0x1800c0b0e  mov     r8d, eax; int
0x1800c0b11  mov     edx, r13d; int
0x1800c0b14  mov     rcx, rdi; struct _IMAGELIST **
0x1800c0b17  call    ?CreateImageListHelper@@YAXPEAPEAU_IMAGELIST@@HH@Z; CreateImageListHelper(_IMAGELIST * *,int,int)
0x1800c0b1c  jmp     loc_1800C0A18
0x1800c0b21  test    rcx, rcx
0x1800c0b24  jz      loc_1800C0A2C
0x1800c0b2a  mov     r8, r14; hicon
0x1800c0b2d  mov     edx, 3; i
0x1800c0b32  call    ImageList_ReplaceIcon
0x1800c0b37  jmp     loc_1800C0A2C
```
