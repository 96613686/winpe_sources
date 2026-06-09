# ClasspPrepareMcnIrp

- ea: `0x14000f630`
- end: `0x14000fccf`
- name: `ClasspPrepareMcnIrp`
- size: `1695`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010040`
- `0x14005479c`

## callees

- `0x14000f3e0`
- `0x14000f630`
- `0x1400134a0`
- `0x14001fbf4`
- `0x14001feac`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoReuseIrp` at `0x14000f6a6`
- `ntoskrnl!IoReuseIrp` at `0x14000f6a6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000f66e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000f66e`

## pseudocode

```c
IRP *__fastcall ClasspPrepareMcnIrp(__int64 a1, __int64 a2, char a3)
{
  IRP *v3; // rbx
  __int64 v7; // rdi
  int v8; // eax
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  _DEVICE_OBJECT *v10; // rax
  _IO_STACK_LOCATION *v11; // rdi
  int v12; // eax
  int v13; // r15d
  bool v14; // zf
  _SECURITY_QUALITY_OF_SERVICE *v15; // r12
  unsigned int v16; // r13d
  _IO_SECURITY_CONTEXT *SecurityContext; // rdi
  _IO_SECURITY_CONTEXT *v19; // rdx
  _IO_STACK_LOCATION *v20; // rax
  int v21; // ecx
  unsigned int v22; // r10d
  __int64 i; // r11
  __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  char *v26; // r9
  __int64 v27; // r8
  int v28; // ecx
  int v29; // ecx
  unsigned int v30; // r10d
  __int64 v31; // r11
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  char *v34; // r9
  __int64 v35; // r8
  int v36; // ecx
  int v37; // ecx
  unsigned int v38; // r10d
  __int64 j; // r11
  __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  char *v42; // r9
  __int64 v43; // r8
  int v44; // ecx
  int v45; // ecx
  unsigned int v46; // r10d
  __int64 v47; // r11
  __int64 v48; // rcx
  unsigned __int64 v49; // r8
  __int64 v50; // r9
  int v51; // ecx
  int v52; // ecx
  unsigned __int64 v53; // rcx
  __int64 v54; // r11
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // rcx
  unsigned __int64 v57; // rcx
  unsigned int AccessState; // r10d
  __int64 v59; // rcx
  unsigned __int64 DesiredAccess; // rdx
  char *v61; // r9
  __int64 v62; // r8
  int v63; // ecx
  _ACCESS_STATE *v64; // [rsp+30h] [rbp-48h]
  unsigned __int8 v65; // [rsp+38h] [rbp-40h]
  char v66; // [rsp+88h] [rbp+10h]
  int v67; // [rsp+98h] [rbp+20h]

  v3 = *(IRP **)(a2 + 112);
  if ( !v3 )
    return 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL);
  if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(*(_QWORD *)(v7 + 440) + 8LL)) )
  {
    _InterlockedIncrement(*(volatile signed __int32 **)(v7 + 440));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_a22cc05f221e30b8049471910da99059_Traceguids,
        **(unsigned int **)(v7 + 440));
    }
  }
  v8 = *(_DWORD *)(v7 + 108);
  if ( v8 == 2 )
    return 0;
  if ( v8 == 1 )
  {
    ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(a1 + 8), v3);
    return 0;
  }
  IoReuseIrp(v3, -1073741637);
  --v3->Tail.Overlay.CurrentStackLocation;
  --v3->CurrentLocation;
  CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
  v10 = *(_DEVICE_OBJECT **)(a1 + 8);
  CurrentStackLocation->Flags |= 2u;
  CurrentStackLocation->DeviceObject = v10;
  v11 = v3->Tail.Overlay.CurrentStackLocation;
  v11[-1].MajorFunction = 15;
  v11[-1].Parameters.WMI.ProviderId = a2 + 120;
  v65 = *(_BYTE *)(a2 + 321);
  v64 = *(_ACCESS_STATE **)(a2 + 304);
  memset(v64, 0, v65);
  v12 = *(_DWORD *)(a1 + 584);
  v13 = *(_DWORD *)(a2 + 312) | *(_DWORD *)(a1 + 592);
  v67 = 2 * v12;
  if ( !(2 * v12) )
  {
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, 0);
      }
      v67 = 2 * *(_DWORD *)(a1 + 584);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
      v67 = 20;
    }
  }
  if ( a3 )
  {
    v11[-1].Parameters.Read.ByteOffset.LowPart = 1769489;
    v13 |= 0x40u;
    v3->MdlAddress = *(_MDL **)(a2 + 88);
    v15 = *(_SECURITY_QUALITY_OF_SERVICE **)(a2 + 80);
    v16 = *(_DWORD *)(a2 + 96);
    v66 = 10;
    v67 = 4;
  }
  else
  {
    v14 = ClasspScreenOff == 1;
    v11[-1].Parameters.Read.ByteOffset.LowPart = 1769491;
    v3->MdlAddress = 0;
    if ( v14 && *(_DWORD *)(*(_QWORD *)(a1 + 8) + 72LL) != 2 )
      v13 |= 0x100000u;
    v15 = 0;
    v66 = 6;
    v16 = 0;
  }
  SecurityContext = v11[-1].Parameters.Create.SecurityContext;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 528) + 30LL) != 1 )
  {
    memset(SecurityContext, 0, 0x58u);
    SecurityContext[1].AccessState = v64;
    BYTE3(SecurityContext->AccessState) = v65;
    SecurityContext->FullCreateOptions = v67;
    BYTE2(SecurityContext->AccessState) = v66;
    LOWORD(SecurityContext->AccessState) = 8447;
    LODWORD(SecurityContext->SecurityQos) = 88;
    BYTE4(SecurityContext->SecurityQos) = 0;
    SecurityContext[2].SecurityQos = (_SECURITY_QUALITY_OF_SERVICE *)v3;
    HIDWORD(SecurityContext->AccessState) = v13;
    SecurityContext[1].SecurityQos = v15;
    SecurityContext->DesiredAccess = v16;
    goto LABEL_14;
  }
  if ( (int)InitializeStorageRequestBlock((__int64)SecurityContext) < 0 )
    return 0;
  v14 = BYTE2(SecurityContext->SecurityQos) == 40;
  SecurityContext[1].DesiredAccess = v67;
  LODWORD(SecurityContext[1].AccessState) = 255;
  HIWORD(SecurityContext[1].AccessState) = 32;
  SecurityContext->FullCreateOptions = 0;
  BYTE3(SecurityContext->SecurityQos) = 0;
  SecurityContext[3].AccessState = (_ACCESS_STATE *)v3;
  LODWORD(SecurityContext[1].SecurityQos) = v13;
  *(_QWORD *)&SecurityContext[2].DesiredAccess = v15;
  HIDWORD(SecurityContext[2].AccessState) = v16;
  if ( v14 )
  {
    AccessState = (unsigned int)SecurityContext[2].AccessState;
    v54 = 0;
    if ( AccessState )
    {
      while ( 1 )
      {
        v59 = *((unsigned int *)&SecurityContext[5].SecurityQos + v54);
        if ( (unsigned int)v59 < 0x80 )
          goto LABEL_77;
        DesiredAccess = SecurityContext->DesiredAccess;
        if ( (unsigned int)v59 >= (unsigned int)DesiredAccess )
          goto LABEL_77;
        v61 = (char *)SecurityContext + v59;
        v62 = (unsigned int)v59;
        v63 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v59);
        if ( v63 == 64 )
          break;
        v21 = v63 - 65;
        if ( !v21 )
        {
          v53 = v62 + 56;
          goto LABEL_76;
        }
        if ( v21 == 1 && v62 + 40 <= DesiredAccess )
        {
LABEL_29:
          v61[8] = 0;
          goto LABEL_30;
        }
LABEL_77:
        v54 = (unsigned int)(v54 + 1);
        if ( (unsigned int)v54 >= AccessState )
          goto LABEL_30;
      }
      v53 = v62 + 40;
LABEL_76:
      if ( v53 <= DesiredAccess )
        goto LABEL_29;
      goto LABEL_77;
    }
  }
  else
  {
    BYTE4(SecurityContext->SecurityQos) = 0;
  }
LABEL_30:
  if ( BYTE2(SecurityContext->SecurityQos) != 40 )
  {
    SecurityContext[1].AccessState = v64;
    goto LABEL_40;
  }
  if ( !SecurityContext->FullCreateOptions )
  {
    v22 = (unsigned int)SecurityContext[2].AccessState;
    for ( i = 0; (unsigned int)i < v22; i = (unsigned int)(i + 1) )
    {
      v24 = *((unsigned int *)&SecurityContext[5].SecurityQos + i);
      if ( (unsigned int)v24 < 0x80 )
        continue;
      v25 = SecurityContext->DesiredAccess;
      if ( (unsigned int)v24 >= (unsigned int)v25 )
        continue;
      v26 = (char *)SecurityContext + v24;
      v27 = (unsigned int)v24;
      v28 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v24);
      if ( v28 == 64 )
      {
        v55 = v27 + 40;
      }
      else
      {
        v29 = v28 - 65;
        if ( v29 )
        {
          if ( v29 == 1 && v27 + 40 <= v25 )
          {
            *((_QWORD *)v26 + 3) = v64;
            break;
          }
          continue;
        }
        v55 = v27 + 56;
      }
      if ( v55 <= v25 )
      {
        *((_QWORD *)v26 + 2) = v64;
        break;
      }
    }
  }
LABEL_40:
  if ( BYTE2(SecurityContext->SecurityQos) == 40 )
  {
    if ( !SecurityContext->FullCreateOptions )
    {
      v30 = (unsigned int)SecurityContext[2].AccessState;
      v31 = 0;
      if ( v30 )
      {
        while ( 1 )
        {
          v32 = *((unsigned int *)&SecurityContext[5].SecurityQos + v31);
          if ( (unsigned int)v32 < 0x80 )
            goto LABEL_85;
          v33 = SecurityContext->DesiredAccess;
          if ( (unsigned int)v32 >= (unsigned int)v33 )
            goto LABEL_85;
          v34 = (char *)SecurityContext + v32;
          v35 = (unsigned int)v32;
          v36 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v32);
          if ( v36 == 64 )
            break;
          v37 = v36 - 65;
          if ( !v37 )
          {
            v56 = v35 + 56;
            goto LABEL_84;
          }
          if ( v37 == 1 && v35 + 40 <= v33 )
          {
LABEL_49:
            v34[9] = v65;
            goto LABEL_50;
          }
LABEL_85:
          v31 = (unsigned int)(v31 + 1);
          if ( (unsigned int)v31 >= v30 )
            goto LABEL_50;
        }
        v56 = v35 + 40;
LABEL_84:
        if ( v56 <= v33 )
          goto LABEL_49;
        goto LABEL_85;
      }
    }
  }
  else
  {
    BYTE3(SecurityContext->AccessState) = v65;
  }
LABEL_50:
  if ( BYTE2(SecurityContext->SecurityQos) != 40 )
  {
    BYTE2(SecurityContext->AccessState) = v66;
    goto LABEL_62;
  }
  if ( !SecurityContext->FullCreateOptions )
  {
    v38 = (unsigned int)SecurityContext[2].AccessState;
    for ( j = 0; (unsigned int)j < v38; j = (unsigned int)(j + 1) )
    {
      v40 = *((unsigned int *)&SecurityContext[5].SecurityQos + j);
      if ( (unsigned int)v40 < 0x80 )
        continue;
      v41 = SecurityContext->DesiredAccess;
      if ( (unsigned int)v40 >= (unsigned int)v41 )
        continue;
      v42 = (char *)SecurityContext + v40;
      v43 = (unsigned int)v40;
      v44 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v40);
      if ( v44 == 64 )
      {
        v57 = v43 + 40;
      }
      else
      {
        v45 = v44 - 65;
        if ( v45 )
        {
          if ( v45 == 1 && v43 + 40 <= v41 )
            break;
          continue;
        }
        v57 = v43 + 56;
      }
      if ( v57 <= v41 )
      {
        v42[10] = v66;
        break;
      }
    }
  }
LABEL_62:
  if ( BYTE2(SecurityContext->SecurityQos) != 40 )
  {
LABEL_14:
    v19 = SecurityContext + 3;
    goto LABEL_15;
  }
  v19 = 0;
  if ( SecurityContext->FullCreateOptions )
    goto LABEL_15;
  v46 = (unsigned int)SecurityContext[2].AccessState;
  if ( !v46 )
    goto LABEL_15;
  v47 = 0;
  while ( 1 )
  {
    v48 = *((unsigned int *)&SecurityContext[5].SecurityQos + v47);
    if ( (unsigned int)v48 < 0x80 )
      goto LABEL_99;
    v49 = SecurityContext->DesiredAccess;
    if ( (unsigned int)v48 >= (unsigned int)v49 )
      goto LABEL_99;
    v50 = (unsigned int)v48;
    v51 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v48);
    if ( v51 != 64 )
      break;
    if ( v50 + 40 <= v49 )
      goto LABEL_91;
LABEL_99:
    v47 = (unsigned int)(v47 + 1);
    if ( (unsigned int)v47 >= v46 )
      goto LABEL_15;
  }
  v52 = v51 - 65;
  if ( v52 )
  {
    if ( v52 == 1 && v50 + 40 <= v49 )
    {
      v19 = (_IO_SECURITY_CONTEXT *)((char *)SecurityContext + v50 + 32);
      if ( !*(_DWORD *)((char *)&SecurityContext->AccessState + v50 + 4) )
        v19 = 0;
      goto LABEL_15;
    }
    goto LABEL_99;
  }
  if ( v50 + 56 > v49 )
    goto LABEL_99;
LABEL_91:
  if ( *((_BYTE *)&SecurityContext->AccessState + v50 + 2) )
    v19 = (_IO_SECURITY_CONTEXT *)((char *)SecurityContext + v50 + 24);
LABEL_15:
  if ( v19 )
  {
    if ( a3 )
    {
      BYTE1(v19->SecurityQos) |= 1u;
      LOBYTE(v19->SecurityQos) = 74;
      HIBYTE(v19->SecurityQos) = BYTE1(*(_DWORD *)(a2 + 96));
      LOBYTE(v19->AccessState) = *(_BYTE *)(a2 + 96);
      BYTE4(v19->SecurityQos) = *(_BYTE *)(a2 + 74);
    }
    else
    {
      LOBYTE(v19->SecurityQos) = 0;
    }
  }
  v20 = v3->Tail.Overlay.CurrentStackLocation;
  v20[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClasspMediaChangeDetectionCompletion;
  v20[-1].Context = SecurityContext;
  v20[-1].Control = -32;
  return v3;
}

```

## disassembly

```asm
0x14000f630  mov     [rsp+arg_0], rbx
0x14000f635  push    rbp
0x14000f636  push    rsi
0x14000f637  push    rdi
0x14000f638  push    r12
0x14000f63a  push    r13
0x14000f63c  push    r14
0x14000f63e  push    r15
0x14000f640  sub     rsp, 40h
0x14000f644  mov     rbx, [rdx+70h]
0x14000f648  movzx   r14d, r8b
0x14000f64c  mov     rbp, rdx
0x14000f64f  mov     rsi, rcx
0x14000f652  test    rbx, rbx
0x14000f655  jz      loc_14000F79F
0x14000f65b  mov     rax, [rcx+8]
0x14000f65f  mov     rdi, [rax+40h]
0x14000f663  mov     rcx, [rdi+1B8h]
0x14000f66a  add     rcx, 8; RunRefCacheAware
0x14000f66e  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14000f675  nop     dword ptr [rax+rax+00h]
0x14000f67a  lea     r12, WPP_GLOBAL_Control
0x14000f681  test    al, al
0x14000f683  jz      loc_14000F89A
0x14000f689  mov     eax, [rdi+6Ch]
0x14000f68c  cmp     eax, 2
0x14000f68f  jz      loc_14000F79F
0x14000f695  cmp     eax, 1
0x14000f698  jz      loc_14000F875
0x14000f69e  mov     edx, 0C00000BBh; Iostatus
0x14000f6a3  mov     rcx, rbx; Irp
0x14000f6a6  call    cs:__imp_IoReuseIrp
0x14000f6ad  nop     dword ptr [rax+rax+00h]
0x14000f6b2  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000f6ba  xor     edx, edx; Val
0x14000f6bc  dec     byte ptr [rbx+43h]
0x14000f6bf  mov     rcx, [rbx+0B8h]
0x14000f6c6  mov     rax, [rsi+8]
0x14000f6ca  or      byte ptr [rcx+2], 2
0x14000f6ce  mov     [rcx+28h], rax
0x14000f6d2  lea     rax, [rbp+78h]
0x14000f6d6  mov     rdi, [rbx+0B8h]
0x14000f6dd  mov     byte ptr [rdi-48h], 0Fh
0x14000f6e1  mov     [rdi-40h], rax
0x14000f6e5  movzx   ecx, byte ptr [rbp+141h]
0x14000f6ec  mov     rax, [rbp+130h]
0x14000f6f3  mov     r8d, ecx; Size
0x14000f6f6  mov     qword ptr [rsp+78h+var_40], rcx
0x14000f6fb  mov     rcx, rax; void *
0x14000f6fe  mov     [rsp+78h+var_48], rax
0x14000f703  call    memset
0x14000f708  mov     eax, [rsi+248h]
0x14000f70e  mov     r15d, [rsi+250h]
0x14000f715  or      r15d, [rbp+138h]
0x14000f71c  lea     ecx, [rax+rax]
0x14000f71f  mov     [rsp+78h+arg_18], ecx
0x14000f726  test    ecx, ecx
0x14000f728  jz      loc_14000FC54
0x14000f72e  test    r14b, r14b
0x14000f731  jnz     loc_14000F7BA
0x14000f737  cmp     cs:ClasspScreenOff, 1
0x14000f73e  mov     dword ptr [rdi-30h], 1B0013h
0x14000f745  mov     qword ptr [rbx+8], 0
0x14000f74d  mov     rax, [rsi+8]
0x14000f751  jz      loc_14000F886
0x14000f757  xor     r12d, r12d
0x14000f75a  mov     [rsp+78h+arg_8], 6
0x14000f762  xor     r13d, r13d
0x14000f765  mov     rax, [rsi+210h]
0x14000f76c  mov     rdi, [rdi-40h]
0x14000f770  mov     rcx, rdi; void *
0x14000f773  cmp     byte ptr [rax+1Eh], 1
0x14000f777  jnz     short loc_14000F7ED
0x14000f779  xor     eax, eax
0x14000f77b  mov     [rsp+78h+var_58], 40h ; '@'
0x14000f783  movzx   edx, ax
0x14000f786  mov     r9d, 1
0x14000f78c  mov     r8d, 0B8h
0x14000f792  call    InitializeStorageRequestBlock
0x14000f797  test    eax, eax
0x14000f799  jns     loc_14000FBCB
0x14000f79f  xor     eax, eax
0x14000f7a1  mov     rbx, [rsp+78h+arg_0]
0x14000f7a9  add     rsp, 40h
0x14000f7ad  pop     r15
0x14000f7af  pop     r14
0x14000f7b1  pop     r13
0x14000f7b3  pop     r12
0x14000f7b5  pop     rdi
0x14000f7b6  pop     rsi
0x14000f7b7  pop     rbp
0x14000f7b8  retn
0x14000f7ba  mov     dword ptr [rdi-30h], 1B0011h
0x14000f7c1  or      r15d, 40h
0x14000f7c5  mov     rax, [rbp+58h]
0x14000f7c9  mov     [rbx+8], rax
0x14000f7cd  mov     r12, [rbp+50h]
0x14000f7d1  mov     r13d, [rbp+60h]
0x14000f7d5  mov     [rsp+78h+arg_8], 0Ah
0x14000f7dd  mov     [rsp+78h+arg_18], 4
0x14000f7e8  jmp     loc_14000F765
0x14000f7ed  mov     esi, 58h ; 'X'
0x14000f7f2  xor     edx, edx; Val
0x14000f7f4  mov     r8d, esi; Size
0x14000f7f7  call    memset
0x14000f7fc  mov     rax, [rsp+78h+var_48]
0x14000f801  mov     [rdi+20h], rax
0x14000f805  mov     rax, qword ptr [rsp+78h+var_40]
0x14000f80a  mov     [rdi+0Bh], al
0x14000f80d  mov     eax, [rsp+78h+arg_18]
0x14000f814  mov     [rdi+14h], eax
0x14000f817  movzx   eax, [rsp+78h+arg_8]
0x14000f81f  mov     [rdi+0Ah], al
0x14000f822  mov     word ptr [rdi+8], 20FFh
0x14000f828  mov     [rdi], esi
0x14000f82a  mov     byte ptr [rdi+4], 0
0x14000f82e  mov     [rdi+30h], rbx
0x14000f832  mov     [rdi+0Ch], r15d
0x14000f836  mov     [rdi+18h], r12
0x14000f83a  mov     [rdi+10h], r13d
0x14000f83e  lea     rdx, [rdi+48h]
0x14000f842  test    rdx, rdx
0x14000f845  jz      short loc_14000F853
0x14000f847  test    r14b, r14b
0x14000f84a  jnz     loc_14000FCAC
0x14000f850  mov     [rdx], r14b
0x14000f853  mov     rax, [rbx+0B8h]
0x14000f85a  lea     rcx, ClasspMediaChangeDetectionCompletion
0x14000f861  mov     [rax-10h], rcx
0x14000f865  mov     [rax-8], rdi
0x14000f869  mov     byte ptr [rax-45h], 0E0h
0x14000f86d  mov     rax, rbx
0x14000f870  jmp     loc_14000F7A1
0x14000f875  mov     rcx, [rsi+8]; DeviceObject
0x14000f879  mov     rdx, rbx; Tag
0x14000f87c  call    ClassReleaseRemoveLock
0x14000f881  jmp     loc_14000F79F
0x14000f886  cmp     dword ptr [rax+48h], 2
0x14000f88a  jz      loc_14000F757
0x14000f890  bts     r15d, 14h
0x14000f895  jmp     loc_14000F757
0x14000f89a  mov     rax, [rdi+1B8h]
0x14000f8a1  lock inc dword ptr [rax]
0x14000f8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8ab  cmp     rcx, r12
0x14000f8ae  jz      loc_14000F689
0x14000f8b4  test    dword ptr [rcx+2Ch], 200h
0x14000f8bb  jz      loc_14000F689
0x14000f8c1  cmp     byte ptr [rcx+29h], 5
0x14000f8c5  jb      loc_14000F689
0x14000f8cb  mov     r9, [rdi+1B8h]
0x14000f8d2  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x14000f8d9  mov     rcx, [rcx+18h]
0x14000f8dd  mov     edx, 0Eh
0x14000f8e2  mov     r9d, [r9]
0x14000f8e5  call    WPP_SF_d
0x14000f8ea  jmp     loc_14000F689
0x14000f8ef  sub     ecx, 41h ; 'A'
0x14000f8f2  jz      loc_14000FAEC
0x14000f8f8  cmp     ecx, 1
0x14000f8fb  jnz     loc_14000FAF9
0x14000f901  lea     rcx, [r8+28h]
0x14000f905  cmp     rcx, rdx
0x14000f908  ja      loc_14000FAF9
0x14000f90e  mov     byte ptr [r9+8], 0
0x14000f913  cmp     byte ptr [rdi+2], 28h ; '('
0x14000f917  jnz     loc_14000FB8A
0x14000f91d  cmp     dword ptr [rdi+14h], 0
0x14000f921  jnz     short loc_14000F986
0x14000f923  mov     r10d, [rdi+38h]
0x14000f927  xor     r11d, r11d
0x14000f92a  test    r10d, r10d
0x14000f92d  jz      short loc_14000F986
0x14000f92f  mov     ecx, [rdi+r11*4+78h]
0x14000f934  cmp     ecx, 80h
0x14000f93a  jb      loc_14000FB17
0x14000f940  mov     edx, [rdi+10h]
0x14000f943  cmp     ecx, edx
0x14000f945  jnb     loc_14000FB17
0x14000f94b  lea     r9, [rcx+rdi]
0x14000f94f  mov     r8d, ecx
0x14000f952  mov     ecx, [r9]
0x14000f955  cmp     ecx, 40h ; '@'
0x14000f958  jz      loc_14000FB84
0x14000f95e  sub     ecx, 41h ; 'A'
0x14000f961  jz      loc_14000FB0A
0x14000f967  cmp     ecx, 1
0x14000f96a  jnz     loc_14000FB17
0x14000f970  lea     rcx, [r8+28h]
0x14000f974  cmp     rcx, rdx
0x14000f977  ja      loc_14000FB17
0x14000f97d  mov     rax, [rsp+78h+var_48]
0x14000f982  mov     [r9+18h], rax
0x14000f986  cmp     byte ptr [rdi+2], 28h ; '('
0x14000f98a  jnz     loc_14000FB9E
0x14000f990  cmp     dword ptr [rdi+14h], 0
0x14000f994  jnz     short loc_14000F9F9
0x14000f996  mov     r10d, [rdi+38h]
0x14000f99a  xor     r11d, r11d
0x14000f99d  test    r10d, r10d
0x14000f9a0  jz      short loc_14000F9F9
0x14000f9a2  mov     ecx, [rdi+r11*4+78h]
0x14000f9a7  cmp     ecx, 80h
0x14000f9ad  jb      loc_14000FB35
0x14000f9b3  mov     edx, [rdi+10h]
0x14000f9b6  cmp     ecx, edx
0x14000f9b8  jnb     loc_14000FB35
0x14000f9be  lea     r9, [rcx+rdi]
0x14000f9c2  mov     r8d, ecx
0x14000f9c5  mov     ecx, [r9]
0x14000f9c8  cmp     ecx, 40h ; '@'
0x14000f9cb  jz      loc_14000FB98
0x14000f9d1  sub     ecx, 41h ; 'A'
0x14000f9d4  jz      loc_14000FB28
0x14000f9da  cmp     ecx, 1
0x14000f9dd  jnz     loc_14000FB35
0x14000f9e3  lea     rcx, [r8+28h]
0x14000f9e7  cmp     rcx, rdx
0x14000f9ea  ja      loc_14000FB35
0x14000f9f0  mov     rax, qword ptr [rsp+78h+var_40]
0x14000f9f5  mov     [r9+9], al
0x14000f9f9  cmp     byte ptr [rdi+2], 28h ; '('
0x14000f9fd  jnz     short loc_14000FA59
0x14000f9ff  cmp     dword ptr [rdi+14h], 0
0x14000fa03  jnz     short loc_14000FA64
0x14000fa05  mov     r10d, [rdi+38h]
0x14000fa09  xor     r11d, r11d
0x14000fa0c  test    r10d, r10d
0x14000fa0f  jz      short loc_14000FA64
0x14000fa11  mov     ecx, [rdi+r11*4+78h]
0x14000fa16  cmp     ecx, 80h
0x14000fa1c  jb      short loc_14000FA4F
0x14000fa1e  mov     edx, [rdi+10h]
0x14000fa21  cmp     ecx, edx
0x14000fa23  jnb     short loc_14000FA4F
0x14000fa25  lea     r9, [rcx+rdi]
0x14000fa29  mov     r8d, ecx
0x14000fa2c  mov     ecx, [r9]
0x14000fa2f  cmp     ecx, 40h ; '@'
0x14000fa32  jz      loc_14000FBAB
0x14000fa38  sub     ecx, 41h ; 'A'
0x14000fa3b  jz      loc_14000FB46
0x14000fa41  cmp     ecx, 1
0x14000fa44  jnz     short loc_14000FA4F
0x14000fa46  lea     rcx, [r8+28h]
0x14000fa4a  cmp     rcx, rdx
0x14000fa4d  jbe     short loc_14000FA64
0x14000fa4f  inc     r11d
0x14000fa52  cmp     r11d, r10d
0x14000fa55  jb      short loc_14000FA11
0x14000fa57  jmp     short loc_14000FA64
0x14000fa59  movzx   eax, [rsp+78h+arg_8]
0x14000fa61  mov     [rdi+0Ah], al
0x14000fa64  cmp     byte ptr [rdi+2], 28h ; '('
0x14000fa68  jnz     loc_14000F83E
0x14000fa6e  xor     edx, edx
0x14000fa70  cmp     [rdi+14h], edx
0x14000fa73  jnz     loc_14000F842
0x14000fa79  mov     r10d, [rdi+38h]
0x14000fa7d  test    r10d, r10d
0x14000fa80  jz      loc_14000F842
0x14000fa86  xor     r11d, r11d
0x14000fa89  mov     ecx, [rdi+r11*4+78h]
0x14000fa8e  cmp     ecx, 80h
0x14000fa94  jb      loc_14000FBBA
0x14000fa9a  mov     r8d, [rdi+10h]
0x14000fa9e  cmp     ecx, r8d
0x14000faa1  jnb     loc_14000FBBA
0x14000faa7  mov     r9d, ecx
0x14000faaa  mov     ecx, [rcx+rdi]
0x14000faad  cmp     ecx, 40h ; '@'
0x14000fab0  jz      loc_14000FB64
0x14000fab6  sub     ecx, 41h ; 'A'
0x14000fab9  jz      loc_14000FBB1
0x14000fabf  cmp     ecx, 1
0x14000fac2  jnz     loc_14000FBBA
0x14000fac8  lea     rcx, [r9+28h]
0x14000facc  cmp     rcx, r8
0x14000facf  ja      loc_14000FBBA
0x14000fad5  xor     eax, eax
0x14000fad7  lea     rdx, [rdi+20h]
0x14000fadb  add     rdx, r9
0x14000fade  cmp     [r9+rdi+0Ch], eax
0x14000fae3  cmovz   rdx, rax
0x14000fae7  jmp     loc_14000F842
0x14000faec  lea     rcx, [r8+38h]
0x14000faf0  cmp     rcx, rdx
0x14000faf3  jbe     loc_14000F90E
0x14000faf9  inc     r11d
0x14000fafc  cmp     r11d, r10d
0x14000faff  jb      loc_14000FC13
0x14000fb05  jmp     loc_14000F913
0x14000fb0a  lea     rcx, [r8+38h]
0x14000fb0e  cmp     rcx, rdx
0x14000fb11  jbe     loc_14000FC9E
0x14000fb17  inc     r11d
0x14000fb1a  cmp     r11d, r10d
0x14000fb1d  jb      loc_14000F92F
0x14000fb23  jmp     loc_14000F986
0x14000fb28  lea     rcx, [r8+38h]
  ... truncated ...
```
