# CMsftWriteEngine2::WriteToRecorder(void)

- ea: `0x180008510`
- end: `0x180008757`
- name: `?WriteToRecorder@CMsftWriteEngine2@@QEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CMsftWriteEngine2 *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800361c8`

## callees

- `0x180002fc8`
- `0x180008510`
- `0x180008760`
- `0x180008954`
- `0x18000f7c4`
- `0x18000f874`
- `0x1800140f4`
- `0x180016778`
- `0x1800236b4`
- `0x180036690`
- `0x18004a010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000867f`
- `KERNEL32!SetEvent` at `0x18000867f`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::WriteToRecorder(CMsftWriteEngine2 *this)
{
  __int64 v1; // rax
  signed int v3; // ebx
  unsigned int v4; // edi
  int v5; // r15d
  const struct _GUID *v6; // r8
  struct IDiscRecorder2Ex *DiscRecorder; // r14
  CWriteEngineSectionResources *v8; // rcx
  int v9; // eax
  __int64 Buffer; // rax
  __int64 v11; // rcx
  unsigned __int8 *v12; // rbx
  unsigned int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v17; // [rsp+70h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 17);
  v3 = 0;
  v4 = *(_DWORD *)(v1 + 28);
  v5 = *(_DWORD *)(v1 + 36);
  DiscRecorder = CWriteEngineStaticDriveInformation::get_DiscRecorderEx(*((CWriteEngineStaticDriveInformation **)this
                                                                        + 15));
  if ( !DiscRecorder )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
    }
    v3 = -1062600701;
  }
  if ( v3 >= 0 )
  {
    while ( v5 > 0 )
    {
      v8 = (CWriteEngineSectionResources *)*((_QWORD *)this + 16);
      v17 = -2097152;
      v9 = CWriteEngineSectionResources::WaitForNextWriteBuffer(v8, &v17);
      v3 = v9;
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            16,
            &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
            (unsigned int)v9);
        }
        break;
      }
      Buffer = CWriteEngineSectionResources::get_Buffer(*((CWriteEngineSectionResources **)this + 16), v17);
      v11 = *((_QWORD *)this + 17);
      v12 = (unsigned __int8 *)Buffer;
      v13 = v5;
      if ( *(_DWORD *)(v11 + 56) <= v5 )
        v13 = *(_DWORD *)(v11 + 56);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 5u )
      {
        WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
      }
      v3 = CMsftWriteEngine2::WriteWithRetries(this, DiscRecorder, v12, v4, v13);
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
        {
          WPP_SF_ddDDd(*((_QWORD *)WPP_GLOBAL_Control + 27), v14, v6, v4, v13 + v4 - 1, v4, v13 + v4 - 1, v3);
        }
        break;
      }
      v4 += v13;
      _InterlockedAdd(
        (volatile signed __int32 *)(*((_QWORD *)this + 18) + 92LL),
        -(*(_DWORD *)(*((_QWORD *)this + 17) + 40LL) * v13));
      v15 = v17;
      *(_DWORD *)(*((_QWORD *)this + 18) + 76LL) = v4 - 1;
      SetEvent(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 16) + 40LL) + 8 * v15));
      v3 = 0;
      v5 -= v13;
    }
  }
  if ( DiscRecorder )
    ((void (__fastcall *)(struct IDiscRecorder2Ex *))DiscRecorder->lpVtbl->Release)(DiscRecorder);
  if ( (v3 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v3, (int)&CLSID_MsftWriteEngine2, v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008510  mov     [rsp+arg_8], rbx
0x180008515  mov     [rsp+arg_10], rbp
0x18000851a  push    rsi
0x18000851b  push    rdi
0x18000851c  push    r13
0x18000851e  push    r14
0x180008520  push    r15
0x180008522  sub     rsp, 40h
0x180008526  mov     rax, [rcx+88h]
0x18000852d  mov     rbp, rcx
0x180008530  mov     rcx, [rcx+78h]; this
0x180008534  xor     ebx, ebx
0x180008536  mov     edi, [rax+1Ch]
0x180008539  mov     r15d, [rax+24h]
0x18000853d  call    ?get_DiscRecorderEx@CWriteEngineStaticDriveInformation@@QEAAPEAUIDiscRecorder2Ex@@XZ; CWriteEngineStaticDriveInformation::get_DiscRecorderEx(void)
0x180008542  lea     r13, WPP_GLOBAL_Control
0x180008549  mov     r14, rax
0x18000854c  test    rax, rax
0x18000854f  jnz     short loc_18000858A
0x180008551  mov     rcx, cs:WPP_GLOBAL_Control
0x180008558  cmp     rcx, r13
0x18000855b  jz      short loc_180008585
0x18000855d  test    byte ptr [rcx+0E4h], 4
0x180008564  jz      short loc_180008585
0x180008566  cmp     byte ptr [rcx+0E1h], 3
0x18000856d  jb      short loc_180008585
0x18000856f  mov     rcx, [rcx+0D8h]
0x180008576  lea     edx, [rbx+0Fh]
0x180008579  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008580  call    WPP_SF_
0x180008585  mov     ebx, 0C0AA0003h
0x18000858a  test    ebx, ebx
0x18000858c  js      loc_18000870C
0x180008592  test    r15d, r15d
0x180008595  jle     loc_18000870C
0x18000859b  mov     rcx, [rbp+80h]; this
0x1800085a2  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x1800085a7  mov     [rsp+68h+arg_0], 0FFE00000h
0x1800085af  call    ?WaitForNextWriteBuffer@CWriteEngineSectionResources@@QEAAJPEAK@Z; CWriteEngineSectionResources::WaitForNextWriteBuffer(ulong *)
0x1800085b4  mov     ebx, eax
0x1800085b6  test    eax, eax
0x1800085b8  js      loc_1800086D3
0x1800085be  mov     edx, [rsp+68h+arg_0]; unsigned int
0x1800085c2  mov     rcx, [rbp+80h]; this
0x1800085c9  call    ?get_Buffer@CWriteEngineSectionResources@@QEAAPEAEK@Z; CWriteEngineSectionResources::get_Buffer(ulong)
0x1800085ce  mov     rcx, [rbp+88h]
0x1800085d5  mov     rbx, rax
0x1800085d8  cmp     [rcx+38h], r15d
0x1800085dc  mov     esi, r15d
0x1800085df  cmovle  esi, [rcx+38h]
0x1800085e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085ea  cmp     rcx, r13
0x1800085ed  jz      short loc_180008628
0x1800085ef  test    byte ptr [rcx+0E4h], 4
0x1800085f6  jz      short loc_180008628
0x1800085f8  cmp     byte ptr [rcx+0E1h], 5
0x1800085ff  jb      short loc_180008628
0x180008601  mov     rcx, [rcx+0D8h]
0x180008608  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x18000860f  mov     [rsp+68h+var_38], edi
0x180008613  mov     edx, 11h
0x180008618  mov     [rsp+68h+var_40], edi
0x18000861c  mov     r9d, esi
0x18000861f  mov     [rsp+68h+var_48], esi
0x180008623  call    WPP_SF_DDDd
0x180008628  mov     r9d, edi; int
0x18000862b  mov     [rsp+68h+var_48], esi; int
0x18000862f  mov     r8, rbx; unsigned __int8 *
0x180008632  mov     rdx, r14; struct IDiscRecorder2Ex *
0x180008635  mov     rcx, rbp; this
0x180008638  call    ?WriteWithRetries@CMsftWriteEngine2@@AEAAJPEAUIDiscRecorder2Ex@@PEAEJJ@Z; CMsftWriteEngine2::WriteWithRetries(IDiscRecorder2Ex *,uchar *,long,long)
0x18000863d  mov     ebx, eax
0x18000863f  test    eax, eax
0x180008641  js      short loc_18000868F
0x180008643  mov     rax, [rbp+88h]
0x18000864a  mov     ecx, esi
0x18000864c  add     edi, esi
0x18000864e  imul    ecx, [rax+28h]
0x180008652  mov     rax, [rbp+90h]
0x180008659  neg     ecx
0x18000865b  lock add [rax+5Ch], ecx
0x18000865f  mov     rax, [rbp+90h]
0x180008666  lea     ecx, [rdi-1]
0x180008669  mov     edx, [rsp+68h+arg_0]
0x18000866d  mov     [rax+4Ch], ecx
0x180008670  mov     rax, [rbp+80h]
0x180008677  mov     rcx, [rax+28h]
0x18000867b  mov     rcx, [rcx+rdx*8]; hEvent
0x18000867f  call    cs:__imp_SetEvent
0x180008685  xor     ebx, ebx
0x180008687  sub     r15d, esi
0x18000868a  jmp     loc_180008592
0x18000868f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008696  cmp     rcx, r13
0x180008699  jz      short loc_18000870C
0x18000869b  test    byte ptr [rcx+0E4h], 4
0x1800086a2  jz      short loc_18000870C
0x1800086a4  cmp     byte ptr [rcx+0E1h], 3
0x1800086ab  jb      short loc_18000870C
0x1800086ad  mov     rcx, [rcx+0D8h]
0x1800086b4  lea     eax, [rdi-1]
0x1800086b7  add     eax, esi
0x1800086b9  mov     [rsp+68h+var_30], ebx
0x1800086bd  mov     [rsp+68h+var_38], eax
0x1800086c1  mov     r9d, edi
0x1800086c4  mov     [rsp+68h+var_40], edi
0x1800086c8  mov     [rsp+68h+var_48], eax
0x1800086cc  call    WPP_SF_ddDDd
0x1800086d1  jmp     short loc_18000870C
0x1800086d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086da  cmp     rcx, r13
0x1800086dd  jz      short loc_18000870C
0x1800086df  test    byte ptr [rcx+0E4h], 4
0x1800086e6  jz      short loc_18000870C
0x1800086e8  cmp     byte ptr [rcx+0E1h], 3
0x1800086ef  jb      short loc_18000870C
0x1800086f1  mov     rcx, [rcx+0D8h]
0x1800086f8  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x1800086ff  mov     edx, 10h
0x180008704  mov     r9d, eax
0x180008707  call    WPP_SF_d
0x18000870c  test    r14, r14
0x18000870f  jz      short loc_180008720
0x180008711  mov     rax, [r14]
0x180008714  mov     rcx, r14
0x180008717  mov     rax, [rax+10h]
0x18000871b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008720  mov     eax, ebx
0x180008722  and     eax, 80FF0000h
0x180008727  cmp     eax, 80AA0000h
0x18000872c  jnz     short loc_18000873C
0x18000872e  lea     rdx, CLSID_MsftWriteEngine2; int
0x180008735  mov     ecx, ebx; dwMessageId
0x180008737  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18000873c  lea     r11, [rsp+68h+var_28]
0x180008741  mov     eax, ebx
0x180008743  mov     rbx, [r11+38h]
0x180008747  mov     rbp, [r11+40h]
0x18000874b  mov     rsp, r11
0x18000874e  pop     r15
0x180008750  pop     r14
0x180008752  pop     r13
0x180008754  pop     rdi
0x180008755  pop     rsi
0x180008756  retn
```
