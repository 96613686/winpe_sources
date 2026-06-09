# sub_1800EECC0

- ea: `0x1800eecc0`
- end: `0x1800ef143`
- name: `sub_1800EECC0`
- size: `1155`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800018b0`
- `0x180005d20`
- `0x18000ae10`
- `0x180022b60`
- `0x180051e44`
- `0x180083a48`
- `0x1800ed7e0`
- `0x1800eecc0`
- `0x180146950`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800eeda0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800eee4c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800eeda0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800eee4c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800eeefb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800eeefb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eed16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eedc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eee6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eef1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eefca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef07e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eed16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eedc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eee6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eef1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800eefca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef07e`

## pseudocode

```c
__int64 __fastcall sub_1800EECC0(PROPVARIANT *a1, const PROPVARIANT *a2)
{
  __int64 v4; // rdx
  bool v5; // zf
  __int64 (__fastcall ***v6)(); // rcx
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(); // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(); // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 (__fastcall ***v20)(); // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 (__fastcall ***v24)(); // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 (__fastcall ***v28)(); // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  char v32; // [rsp+58h] [rbp+10h] BYREF
  LPSTREAM v33; // [rsp+60h] [rbp+18h] BYREF

  sub_18000AE10(&v32, "CWMThumbnailStreamProperty::SetShellValue", 516);
  v5 = a2->vt == 66;
  v33 = 0;
  if ( v5 )
  {
    v7 = PropVariantClear(a1 + 4);
    if ( v7 >= 0 )
    {
      v7 = PropVariantClear(a1 + 5);
      if ( v7 >= 0 )
      {
        v7 = PropVariantCopy(a1 + 4, a2);
        if ( v7 >= 0 )
        {
          v7 = sub_1800ED7E0((__int64)a1, a2->hVal.QuadPart, &v33);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(PROPVARIANT *, LPSTREAM))(*(_QWORD *)&a1->vt + 312LL))(a1, v33);
            if ( v7 < 0 )
            {
              v28 = (__int64 (__fastcall ***)())qword_180171350;
              if ( !qword_180171350 )
              {
                v29 = MFGetCallStackTracingWeakReference(0, v27);
                qword_180171350 = v29;
                if ( v29 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                {
                  v28 = (__int64 (__fastcall ***)())qword_180171350;
                }
                else
                {
                  v28 = &off_1801703B0;
                  qword_180171350 = (__int64)&off_1801703B0;
                }
              }
              if ( *((_BYTE *)v28 + 8) )
              {
                v30 = sub_1800018B0(v28);
                if ( *(_DWORD *)(v30 + 1996) != v7 )
                  sub_180083A48(v30, "CWMThumbnailStreamProperty::SetShellValue", 534, (unsigned int)v7);
              }
              if ( byte_1801712C8 )
              {
                v10 = 51;
                goto LABEL_67;
              }
            }
          }
          else
          {
            v24 = (__int64 (__fastcall ***)())qword_180171350;
            if ( !qword_180171350 )
            {
              v25 = MFGetCallStackTracingWeakReference(0, v23);
              qword_180171350 = v25;
              if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (__int64 (__fastcall ***)())qword_180171350;
              }
              else
              {
                v24 = &off_1801703B0;
                qword_180171350 = (__int64)&off_1801703B0;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = sub_1800018B0(v24);
              if ( *(_DWORD *)(v26 + 1996) != v7 )
                sub_180083A48(v26, "CWMThumbnailStreamProperty::SetShellValue", 532, (unsigned int)v7);
            }
            if ( byte_1801712C8 )
            {
              v10 = 50;
              goto LABEL_67;
            }
          }
        }
        else
        {
          v20 = (__int64 (__fastcall ***)())qword_180171350;
          if ( !qword_180171350 )
          {
            v21 = MFGetCallStackTracingWeakReference(0, v19);
            qword_180171350 = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 (__fastcall ***)())qword_180171350;
            }
            else
            {
              v20 = &off_1801703B0;
              qword_180171350 = (__int64)&off_1801703B0;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = sub_1800018B0(v20);
            if ( *(_DWORD *)(v22 + 1996) != v7 )
              sub_180083A48(v22, "CWMThumbnailStreamProperty::SetShellValue", 530, (unsigned int)v7);
          }
          if ( byte_1801712C8 )
          {
            v10 = 49;
            goto LABEL_67;
          }
        }
      }
      else
      {
        v16 = (__int64 (__fastcall ***)())qword_180171350;
        if ( !qword_180171350 )
        {
          v17 = MFGetCallStackTracingWeakReference(0, v15);
          qword_180171350 = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 (__fastcall ***)())qword_180171350;
          }
          else
          {
            v16 = &off_1801703B0;
            qword_180171350 = (__int64)&off_1801703B0;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = sub_1800018B0(v16);
          if ( *(_DWORD *)(v18 + 1996) != v7 )
            sub_180083A48(v18, "CWMThumbnailStreamProperty::SetShellValue", 528, (unsigned int)v7);
        }
        if ( byte_1801712C8 )
        {
          v10 = 48;
          goto LABEL_67;
        }
      }
    }
    else
    {
      v12 = (__int64 (__fastcall ***)())qword_180171350;
      if ( !qword_180171350 )
      {
        v13 = MFGetCallStackTracingWeakReference(0, v11);
        qword_180171350 = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 (__fastcall ***)())qword_180171350;
        }
        else
        {
          v12 = &off_1801703B0;
          qword_180171350 = (__int64)&off_1801703B0;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = sub_1800018B0(v12);
        if ( *(_DWORD *)(v14 + 1996) != v7 )
          sub_180083A48(v14, "CWMThumbnailStreamProperty::SetShellValue", 527, (unsigned int)v7);
      }
      if ( byte_1801712C8 )
      {
        v10 = 47;
        goto LABEL_67;
      }
    }
  }
  else
  {
    v6 = (__int64 (__fastcall ***)())qword_180171350;
    v7 = -2147024809;
    if ( !qword_180171350 )
    {
      v8 = MFGetCallStackTracingWeakReference(0, v4);
      qword_180171350 = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v6 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v9 = sub_1800018B0(v6);
      if ( *(_DWORD *)(v9 + 1996) != -2147024809 )
        sub_180083A48(v9, "CWMThumbnailStreamProperty::SetShellValue", 524, 2147942487LL);
    }
    if ( byte_1801712C8 )
    {
      v10 = 46;
LABEL_67:
      sub_180051E44(*((_QWORD *)RequestContext + 2), v10, qword_180162120, a1, v7);
    }
  }
  sub_180022B60(&v33);
  sub_180005D20();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800eecc0  mov     [rsp+arg_0], rbx
0x1800eecc5  mov     [rsp+arg_18], rbp
0x1800eecca  push    rsi
0x1800eeccb  push    rdi
0x1800eeccc  push    r15
0x1800eecce  sub     rsp, 30h
0x1800eecd2  mov     rsi, rdx
0x1800eecd5  lea     r15, aCwmthumbnailst_3; "CWMThumbnailStreamProperty::SetShellVal"...
0x1800eecdc  mov     rdi, rcx
0x1800eecdf  mov     rdx, r15
0x1800eece2  mov     r8d, 204h
0x1800eece8  lea     rcx, [rsp+48h+arg_8]
0x1800eeced  call    sub_18000AE10
0x1800eecf2  cmp     word ptr [rsi], 42h ; 'B'
0x1800eecf6  mov     [rsp+48h+arg_10], 0
0x1800eecff  jz      loc_1800EED9C
0x1800eed05  mov     rcx, cs:qword_180171350
0x1800eed0c  mov     ebx, 80070057h
0x1800eed11  test    rcx, rcx
0x1800eed14  jnz     short loc_1800EED5E
0x1800eed16  call    cs:MFGetCallStackTracingWeakReference
0x1800eed1d  nop     dword ptr [rax+rax+00h]
0x1800eed22  mov     cs:qword_180171350, rax
0x1800eed29  mov     rcx, rax
0x1800eed2c  test    rax, rax
0x1800eed2f  jz      short loc_1800EED50
0x1800eed31  mov     rax, [rax]
0x1800eed34  mov     edx, 7F0h
0x1800eed39  mov     rax, [rax+8]
0x1800eed3d  call    cs:__guard_dispatch_icall_fptr
0x1800eed43  test    eax, eax
0x1800eed45  jz      short loc_1800EED50
0x1800eed47  mov     rcx, cs:qword_180171350
0x1800eed4e  jmp     short loc_1800EED5E
0x1800eed50  lea     rcx, off_1801703B0
0x1800eed57  mov     cs:qword_180171350, rcx
0x1800eed5e  cmp     byte ptr [rcx+8], 0
0x1800eed62  jz      short loc_1800EED85
0x1800eed64  call    sub_1800018B0
0x1800eed69  cmp     [rax+7CCh], ebx
0x1800eed6f  jz      short loc_1800EED85
0x1800eed71  mov     r9d, ebx
0x1800eed74  mov     r8d, 20Ch
0x1800eed7a  mov     rdx, r15
0x1800eed7d  mov     rcx, rax
0x1800eed80  call    sub_180083A48
0x1800eed85  cmp     cs:byte_1801712C8, 1
0x1800eed8c  jb      loc_1800EF119
0x1800eed92  mov     edx, 2Eh ; '.'
0x1800eed97  jmp     loc_1800EF0FB
0x1800eed9c  lea     rcx, [rdi+60h]; pvar
0x1800eeda0  call    cs:PropVariantClear
0x1800eeda7  nop     dword ptr [rax+rax+00h]
0x1800eedac  mov     ebx, eax
0x1800eedae  test    eax, eax
0x1800eedb0  jns     loc_1800EEE48
0x1800eedb6  mov     rcx, cs:qword_180171350
0x1800eedbd  test    rcx, rcx
0x1800eedc0  jnz     short loc_1800EEE0A
0x1800eedc2  call    cs:MFGetCallStackTracingWeakReference
0x1800eedc9  nop     dword ptr [rax+rax+00h]
0x1800eedce  mov     cs:qword_180171350, rax
0x1800eedd5  mov     rcx, rax
0x1800eedd8  test    rax, rax
0x1800eeddb  jz      short loc_1800EEDFC
0x1800eeddd  mov     rax, [rax]
0x1800eede0  mov     edx, 7F0h
0x1800eede5  mov     rax, [rax+8]
0x1800eede9  call    cs:__guard_dispatch_icall_fptr
0x1800eedef  test    eax, eax
0x1800eedf1  jz      short loc_1800EEDFC
0x1800eedf3  mov     rcx, cs:qword_180171350
0x1800eedfa  jmp     short loc_1800EEE0A
0x1800eedfc  lea     rcx, off_1801703B0
0x1800eee03  mov     cs:qword_180171350, rcx
0x1800eee0a  cmp     byte ptr [rcx+8], 0
0x1800eee0e  jz      short loc_1800EEE31
0x1800eee10  call    sub_1800018B0
0x1800eee15  cmp     [rax+7CCh], ebx
0x1800eee1b  jz      short loc_1800EEE31
0x1800eee1d  mov     r9d, ebx
0x1800eee20  mov     r8d, 20Fh
0x1800eee26  mov     rdx, r15
0x1800eee29  mov     rcx, rax
0x1800eee2c  call    sub_180083A48
0x1800eee31  cmp     cs:byte_1801712C8, 1
0x1800eee38  jb      loc_1800EF119
0x1800eee3e  mov     edx, 2Fh ; '/'
0x1800eee43  jmp     loc_1800EF0FB
0x1800eee48  lea     rcx, [rdi+78h]; pvar
0x1800eee4c  call    cs:PropVariantClear
0x1800eee53  nop     dword ptr [rax+rax+00h]
0x1800eee58  mov     ebx, eax
0x1800eee5a  test    eax, eax
0x1800eee5c  jns     loc_1800EEEF4
0x1800eee62  mov     rcx, cs:qword_180171350
0x1800eee69  test    rcx, rcx
0x1800eee6c  jnz     short loc_1800EEEB6
0x1800eee6e  call    cs:MFGetCallStackTracingWeakReference
0x1800eee75  nop     dword ptr [rax+rax+00h]
0x1800eee7a  mov     cs:qword_180171350, rax
0x1800eee81  mov     rcx, rax
0x1800eee84  test    rax, rax
0x1800eee87  jz      short loc_1800EEEA8
0x1800eee89  mov     rax, [rax]
0x1800eee8c  mov     edx, 7F0h
0x1800eee91  mov     rax, [rax+8]
0x1800eee95  call    cs:__guard_dispatch_icall_fptr
0x1800eee9b  test    eax, eax
0x1800eee9d  jz      short loc_1800EEEA8
0x1800eee9f  mov     rcx, cs:qword_180171350
0x1800eeea6  jmp     short loc_1800EEEB6
0x1800eeea8  lea     rcx, off_1801703B0
0x1800eeeaf  mov     cs:qword_180171350, rcx
0x1800eeeb6  cmp     byte ptr [rcx+8], 0
0x1800eeeba  jz      short loc_1800EEEDD
0x1800eeebc  call    sub_1800018B0
0x1800eeec1  cmp     [rax+7CCh], ebx
0x1800eeec7  jz      short loc_1800EEEDD
0x1800eeec9  mov     r9d, ebx
0x1800eeecc  mov     r8d, 210h
0x1800eeed2  mov     rdx, r15
0x1800eeed5  mov     rcx, rax
0x1800eeed8  call    sub_180083A48
0x1800eeedd  cmp     cs:byte_1801712C8, 1
0x1800eeee4  jb      loc_1800EF119
0x1800eeeea  mov     edx, 30h ; '0'
0x1800eeeef  jmp     loc_1800EF0FB
0x1800eeef4  mov     rdx, rsi; pvarSrc
0x1800eeef7  lea     rcx, [rdi+60h]; pvarDest
0x1800eeefb  call    cs:PropVariantCopy
0x1800eef02  nop     dword ptr [rax+rax+00h]
0x1800eef07  mov     ebx, eax
0x1800eef09  test    eax, eax
0x1800eef0b  jns     loc_1800EEFA3
0x1800eef11  mov     rcx, cs:qword_180171350
0x1800eef18  test    rcx, rcx
0x1800eef1b  jnz     short loc_1800EEF65
0x1800eef1d  call    cs:MFGetCallStackTracingWeakReference
0x1800eef24  nop     dword ptr [rax+rax+00h]
0x1800eef29  mov     cs:qword_180171350, rax
0x1800eef30  mov     rcx, rax
0x1800eef33  test    rax, rax
0x1800eef36  jz      short loc_1800EEF57
0x1800eef38  mov     rax, [rax]
0x1800eef3b  mov     edx, 7F0h
0x1800eef40  mov     rax, [rax+8]
0x1800eef44  call    cs:__guard_dispatch_icall_fptr
0x1800eef4a  test    eax, eax
0x1800eef4c  jz      short loc_1800EEF57
0x1800eef4e  mov     rcx, cs:qword_180171350
0x1800eef55  jmp     short loc_1800EEF65
0x1800eef57  lea     rcx, off_1801703B0
0x1800eef5e  mov     cs:qword_180171350, rcx
0x1800eef65  cmp     byte ptr [rcx+8], 0
0x1800eef69  jz      short loc_1800EEF8C
0x1800eef6b  call    sub_1800018B0
0x1800eef70  cmp     [rax+7CCh], ebx
0x1800eef76  jz      short loc_1800EEF8C
0x1800eef78  mov     r9d, ebx
0x1800eef7b  mov     r8d, 212h
0x1800eef81  mov     rdx, r15
0x1800eef84  mov     rcx, rax
0x1800eef87  call    sub_180083A48
0x1800eef8c  cmp     cs:byte_1801712C8, 1
0x1800eef93  jb      loc_1800EF119
0x1800eef99  mov     edx, 31h ; '1'
0x1800eef9e  jmp     loc_1800EF0FB
0x1800eefa3  mov     rdx, [rsi+8]
0x1800eefa7  lea     r8, [rsp+48h+arg_10]
0x1800eefac  mov     rcx, rdi
0x1800eefaf  call    sub_1800ED7E0
0x1800eefb4  mov     ebx, eax
0x1800eefb6  test    eax, eax
0x1800eefb8  jns     loc_1800EF050
0x1800eefbe  mov     rcx, cs:qword_180171350
0x1800eefc5  test    rcx, rcx
0x1800eefc8  jnz     short loc_1800EF012
0x1800eefca  call    cs:MFGetCallStackTracingWeakReference
0x1800eefd1  nop     dword ptr [rax+rax+00h]
0x1800eefd6  mov     cs:qword_180171350, rax
0x1800eefdd  mov     rcx, rax
0x1800eefe0  test    rax, rax
0x1800eefe3  jz      short loc_1800EF004
0x1800eefe5  mov     rax, [rax]
0x1800eefe8  mov     edx, 7F0h
0x1800eefed  mov     rax, [rax+8]
0x1800eeff1  call    cs:__guard_dispatch_icall_fptr
0x1800eeff7  test    eax, eax
0x1800eeff9  jz      short loc_1800EF004
0x1800eeffb  mov     rcx, cs:qword_180171350
0x1800ef002  jmp     short loc_1800EF012
0x1800ef004  lea     rcx, off_1801703B0
0x1800ef00b  mov     cs:qword_180171350, rcx
0x1800ef012  cmp     byte ptr [rcx+8], 0
0x1800ef016  jz      short loc_1800EF039
0x1800ef018  call    sub_1800018B0
0x1800ef01d  cmp     [rax+7CCh], ebx
0x1800ef023  jz      short loc_1800EF039
0x1800ef025  mov     r9d, ebx
0x1800ef028  mov     r8d, 214h
0x1800ef02e  mov     rdx, r15
0x1800ef031  mov     rcx, rax
0x1800ef034  call    sub_180083A48
0x1800ef039  cmp     cs:byte_1801712C8, 1
0x1800ef040  jb      loc_1800EF119
0x1800ef046  mov     edx, 32h ; '2'
0x1800ef04b  jmp     loc_1800EF0FB
0x1800ef050  mov     rax, [rdi]
0x1800ef053  mov     rcx, rdi
0x1800ef056  mov     rdx, [rsp+48h+arg_10]
0x1800ef05b  mov     rax, [rax+138h]
0x1800ef062  call    cs:__guard_dispatch_icall_fptr
0x1800ef068  mov     ebx, eax
0x1800ef06a  test    eax, eax
0x1800ef06c  jns     loc_1800EF119
0x1800ef072  mov     rcx, cs:qword_180171350
0x1800ef079  test    rcx, rcx
0x1800ef07c  jnz     short loc_1800EF0C6
0x1800ef07e  call    cs:MFGetCallStackTracingWeakReference
0x1800ef085  nop     dword ptr [rax+rax+00h]
0x1800ef08a  mov     cs:qword_180171350, rax
0x1800ef091  mov     rcx, rax
0x1800ef094  test    rax, rax
0x1800ef097  jz      short loc_1800EF0B8
0x1800ef099  mov     rax, [rax]
0x1800ef09c  mov     edx, 7F0h
0x1800ef0a1  mov     rax, [rax+8]
0x1800ef0a5  call    cs:__guard_dispatch_icall_fptr
0x1800ef0ab  test    eax, eax
0x1800ef0ad  jz      short loc_1800EF0B8
0x1800ef0af  mov     rcx, cs:qword_180171350
0x1800ef0b6  jmp     short loc_1800EF0C6
0x1800ef0b8  lea     rcx, off_1801703B0
0x1800ef0bf  mov     cs:qword_180171350, rcx
0x1800ef0c6  cmp     byte ptr [rcx+8], 0
0x1800ef0ca  jz      short loc_1800EF0ED
0x1800ef0cc  call    sub_1800018B0
0x1800ef0d1  cmp     [rax+7CCh], ebx
0x1800ef0d7  jz      short loc_1800EF0ED
0x1800ef0d9  mov     r9d, ebx
0x1800ef0dc  mov     r8d, 216h
0x1800ef0e2  mov     rdx, r15
0x1800ef0e5  mov     rcx, rax
0x1800ef0e8  call    sub_180083A48
0x1800ef0ed  cmp     cs:byte_1801712C8, 1
0x1800ef0f4  jb      short loc_1800EF119
0x1800ef0f6  mov     edx, 33h ; '3'
0x1800ef0fb  mov     rcx, cs:RequestContext
0x1800ef102  lea     r8, qword_180162120
0x1800ef109  mov     r9, rdi
0x1800ef10c  mov     [rsp+48h+var_28], ebx
0x1800ef110  mov     rcx, [rcx+10h]
0x1800ef114  call    sub_180051E44
0x1800ef119  lea     rcx, [rsp+48h+arg_10]
0x1800ef11e  call    sub_180022B60
0x1800ef123  lea     rcx, [rsp+48h+arg_8]
0x1800ef128  call    sub_180005D20
0x1800ef12d  mov     rbp, [rsp+48h+arg_18]
0x1800ef132  mov     eax, ebx
0x1800ef134  mov     rbx, [rsp+48h+arg_0]
0x1800ef139  add     rsp, 30h
0x1800ef13d  pop     r15
0x1800ef13f  pop     rdi
0x1800ef140  pop     rsi
0x1800ef141  retn
```
