# HidpWriteReport

- ea: `0x1800043a0`
- end: `0x180004bed`
- name: `HidpWriteReport`
- size: `2125`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004c00`
- `0x180006ac8`

## callees

- `0x180003090`
- `0x1800043a0`
- `0x180006780`
- `0x18000c44c`
- `0x1800127d0`
- `0x180013860`
- `0x1800163bc`
- `0x180021bb0`
- `0x180022ffc`
- `0x180027c80`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x180004b33`
- `ntoskrnl!KeBugCheckEx` at `0x180004b33`
- `ntoskrnl!IoIncrementKeepAliveCount` at `0x180004aee`
- `ntoskrnl!IoIncrementKeepAliveCount` at `0x180004aee`
- `ntoskrnl!ExAllocatePool2` at `0x18000452d`
- `ntoskrnl!ExAllocatePool2` at `0x18000452d`

## pseudocode

```c
__int64 __fastcall HidpWriteReport(
        __int64 *a1,
        __int64 a2,
        ULONG_PTR a3,
        _BYTE *a4,
        unsigned int a5,
        char a6,
        _BYTE *a7)
{
  ULONG_PTR v8; // rbx
  __int64 v9; // rbp
  __int64 v11; // rdi
  __int64 v12; // r13
  __int64 v13; // r9
  unsigned int v14; // r12d
  __int64 i; // rdx
  __int64 v16; // r8
  _BYTE *v17; // r9
  _BYTE *v18; // rax
  unsigned int v19; // esi
  unsigned __int8 v20; // cl
  unsigned __int8 v21; // r12
  unsigned int v22; // r8d
  __int64 j; // rax
  unsigned __int8 *v24; // rdx
  unsigned int v25; // ecx
  int v26; // ebp
  unsigned int v27; // esi
  __int64 Pool2; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // ebp
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rcx
  unsigned __int8 *v35; // rax
  __int64 v36; // r15
  __int64 v37; // rbp
  int v38; // edx
  int v39; // r8d
  unsigned int v40; // r14d
  int v42; // edx
  int v43; // r8d
  _BYTE *v44; // [rsp+88h] [rbp-40h]
  __int64 v45; // [rsp+D8h] [rbp+10h]

  v45 = a2;
  v8 = a3;
  v9 = a2;
  *a7 = 0;
  if ( !a4 || !a5 )
    return (unsigned int)-1073741592;
  v11 = 0;
  v12 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 48LL);
  if ( v12 )
  {
    v11 = *(_QWORD *)(v12 + 24);
    if ( !v11 )
    {
      v40 = -1073741727;
      LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          a2,
          a3,
          a1[84],
          3,
          8,
          94,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v9 + 64) + 32LL),
          *(_DWORD *)(v9 + 8),
          *(_QWORD *)(v9 + 48),
          97);
      }
      return v40;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 168));
  }
  v13 = a1[20];
  v14 = *(_DWORD *)(a2 + 8);
  if ( v13 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 42); i = (unsigned int)(i + 1) )
    {
      v16 = v13 + 40 * i;
      if ( *(unsigned __int8 *)(v16 + 4) == v14 )
      {
        if ( !v16 )
          break;
        if ( *(_WORD *)(v16 + 22) )
        {
          v17 = (_BYTE *)a1[22];
          v18 = a4 + 1;
          v19 = a5 - 1;
          if ( *v17 )
          {
            v18 = a4;
            v19 = a5;
          }
          v20 = 0;
          v44 = v18;
          if ( *v17 )
            v20 = *a4;
          v21 = v20;
          if ( v17 )
          {
            v22 = *((_DWORD *)a1 + 46);
            for ( j = 0; (unsigned int)j < v22; j = (unsigned int)(j + 1) )
            {
              v24 = &v17[8 * j];
              if ( *v24 == v20 )
              {
                if ( !v24 )
                  break;
                if ( v12 && v24[1] != *(_DWORD *)v11 )
                {
                  v40 = -1073741808;
                  LOBYTE(v24) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
                  if ( (_BYTE)v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_qdqqdd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      (_DWORD)v24,
                      v22,
                      a1[84],
                      3,
                      8,
                      97);
                  }
                }
                else
                {
                  v25 = *((unsigned __int16 *)v24 + 2);
                  if ( (_WORD)v25 && (v26 = *((unsigned __int16 *)v24 + 2), v19 >= v25) )
                  {
                    v27 = 24;
                    if ( !a6 )
                      v27 = 16;
                    Pool2 = ExAllocatePool2(64, v27, 1130654024);
                    if ( Pool2 )
                    {
                      *(_DWORD *)(Pool2 + 8) = v26;
                      v31 = 721507;
                      *(_QWORD *)Pool2 = v44;
                      *(_BYTE *)(Pool2 + 12) = v21;
                      if ( !a6 )
                        v31 = 720911;
                      *(_QWORD *)(v8 + 112) = Pool2;
                      if ( a6 )
                      {
                        *(_DWORD *)(Pool2 + 16) |= 1u;
                        *(_DWORD *)(Pool2 + 20) = 0;
                      }
                      v32 = *(_QWORD *)(v8 + 184);
                      *(_BYTE *)(v32 - 72) = 15;
                      *(_DWORD *)(v32 - 48) = v31;
                      *(_DWORD *)(v32 - 56) = v27;
                      v33 = *(_QWORD *)(v8 + 184);
                      *(_QWORD *)(v33 - 16) = HidpInterruptWriteComplete;
                      *(_QWORD *)(v33 - 8) = v45;
                      *(_BYTE *)(v33 - 69) = -32;
                      if ( v12 )
                      {
                        v29 = *(_QWORD *)(v11 + 136);
                        if ( v29 )
                        {
                          IoIncrementKeepAliveCount(*(_QWORD *)(v11 + 96));
                          _InterlockedIncrement((volatile signed __int32 *)(v11 + 144));
                        }
                      }
                      LOBYTE(v29) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                      LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      if ( (_BYTE)v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        WPP_RECORDER_AND_TRACE_SF_qdqqdL(WPP_GLOBAL_Control->AttachedDevice, v29, v30, a1[84]);
                      v34 = *a1;
                      if ( (char)--*(_BYTE *)(v8 + 67) <= 0 )
                        KeBugCheckEx(0x35u, v8, 0, 0, 0);
                      *(_QWORD *)(v8 + 184) -= 72LL;
                      v35 = *(unsigned __int8 **)(v8 + 184);
                      v36 = *v35;
                      *((_QWORD *)v35 + 5) = v34;
                      v37 = *(_QWORD *)(v34 + 64);
                      v40 = (*(__int64 (__fastcall **)(__int64, ULONG_PTR, __int64))(*(_QWORD *)(v37 + 40) + 8 * v36 + 32))(
                              v34,
                              v8,
                              v30);
                      if ( *(_BYTE *)(v37 + 24) )
                        v37 = *(_QWORD *)(v37 + 96);
                      LOBYTE(v38) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
                      LOBYTE(v39) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
                      if ( (_BYTE)v38 || (_BYTE)v39 )
                        WPP_RECORDER_AND_TRACE_SF_qqcd(
                          WPP_GLOBAL_Control->AttachedDevice,
                          v38,
                          v39,
                          *(_QWORD *)(v37 + 704),
                          5,
                          4,
                          10,
                          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                          *(_QWORD *)(v37 + 32),
                          v8,
                          v36,
                          v40);
                      *a7 = 1;
                    }
                    else
                    {
                      v40 = -1073741670;
                      LOBYTE(v29) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                      if ( (_BYTE)v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                        WPP_RECORDER_AND_TRACE_SF_qdqqd(
                          WPP_GLOBAL_Control->AttachedDevice,
                          v29,
                          v30,
                          a1[84],
                          2,
                          8,
                          99,
                          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                          *(_QWORD *)(*(_QWORD *)(v45 + 64) + 32LL),
                          *(_DWORD *)(v45 + 8),
                          *(_QWORD *)(v45 + 48),
                          v8,
                          -1073741670);
                      }
                    }
                  }
                  else
                  {
                    v40 = -1073741811;
                    LOBYTE(v24) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
                    if ( (_BYTE)v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      WPP_RECORDER_AND_TRACE_SF_qdqqdHDd(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v24, v22, a1[84]);
                    }
                  }
                }
                return v40;
              }
            }
          }
          TraceLoggingGetReportIdentifierFailed(a1, v20);
          v40 = -1073741811;
          LOBYTE(v42) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
          if ( (_BYTE)v42 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v43) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qdqqdd(WPP_GLOBAL_Control->AttachedDevice, v42, v43, a1[84], 3, 8, 96);
          }
        }
        else
        {
          v40 = -1073741808;
          LOBYTE(i) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
          if ( (_BYTE)i || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qdqL(
              WPP_GLOBAL_Control->AttachedDevice,
              i,
              v16,
              a1[84],
              3,
              8,
              95,
              (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
              *(_QWORD *)(*(_QWORD *)(v9 + 64) + 32LL),
              v14,
              *(_QWORD *)(v9 + 48),
              16);
          }
        }
        return v40;
      }
    }
  }
  TraceLoggingGetCollectionDescFailed(a1, v14);
  return (unsigned int)-1073741667;
}

```

## disassembly

```asm
0x1800043a0  mov     [rsp+arg_0], rbx
0x1800043a5  mov     [rsp+arg_8], rdx
0x1800043aa  push    rbp
0x1800043ab  push    rsi
0x1800043ac  push    rdi
0x1800043ad  push    r12
0x1800043af  push    r13
0x1800043b1  push    r14
0x1800043b3  push    r15
0x1800043b5  sub     rsp, 90h
0x1800043bc  mov     rax, [rsp+0C8h+arg_30]
0x1800043c4  mov     r11, r9
0x1800043c7  mov     rbx, r8
0x1800043ca  mov     rbp, rdx
0x1800043cd  mov     r15, rcx
0x1800043d0  mov     byte ptr [rax], 0
0x1800043d3  test    r9, r9
0x1800043d6  jz      loc_18000482D
0x1800043dc  mov     r10d, [rsp+0C8h+arg_20]
0x1800043e4  test    r10d, r10d
0x1800043e7  jz      loc_18000482D
0x1800043ed  mov     rax, [r8+0B8h]
0x1800043f4  xor     edi, edi
0x1800043f6  mov     r13, [rax+30h]
0x1800043fa  test    r13, r13
0x1800043fd  jz      short loc_180004413
0x1800043ff  mov     rdi, [r13+18h]
0x180004403  test    rdi, rdi
0x180004406  jz      loc_1800048DC
0x18000440c  lock inc dword ptr [rdi+0A8h]
0x180004413  mov     r9, [rcx+0A0h]
0x18000441a  mov     r12d, [rdx+8]
0x18000441e  mov     [rsp+0C8h+arg_18], r12d
0x180004426  test    r9, r9
0x180004429  jz      loc_1800048C6
0x18000442f  mov     esi, [rcx+0A8h]
0x180004435  xor     edx, edx
0x180004437  cmp     edx, esi
0x180004439  jnb     loc_1800048C6
0x18000443f  lea     rcx, [rdx+rdx*4]
0x180004443  movzx   eax, byte ptr [r9+rcx*8+4]
0x180004449  lea     r8, [r9+rcx*8]
0x18000444d  cmp     eax, r12d
0x180004450  jnz     short loc_1800044CF
0x180004452  test    r8, r8
0x180004455  jz      loc_1800048C6
0x18000445b  cmp     word ptr [r8+16h], 0
0x180004461  jz      loc_18000497E
0x180004467  mov     r9, [r15+0B0h]
0x18000446e  lea     rax, [r11+1]
0x180004472  lea     esi, [r10-1]
0x180004476  movzx   edx, byte ptr [r9]
0x18000447a  test    dl, dl
0x18000447c  cmovnz  rax, r11
0x180004480  cmovnz  esi, r10d
0x180004484  xor     ecx, ecx
0x180004486  mov     [rsp+0C8h+var_40], rax
0x18000448e  movzx   eax, byte ptr [r11]
0x180004492  test    dl, dl
0x180004494  mov     [rsp+0C8h+var_48], esi
0x18000449b  cmovnz  ecx, eax
0x18000449e  movzx   r12d, cl
0x1800044a2  test    r9, r9
0x1800044a5  jz      loc_1800046E3
0x1800044ab  mov     r8d, [r15+0B8h]
0x1800044b2  xor     eax, eax
0x1800044b4  cmp     eax, r8d
0x1800044b7  jnb     loc_1800046E3
0x1800044bd  movzx   ecx, byte ptr [r9+rax*8]
0x1800044c2  lea     rdx, [r9+rax*8]
0x1800044c6  cmp     ecx, r12d
0x1800044c9  jz      short loc_1800044D6
0x1800044cb  inc     eax
0x1800044cd  jmp     short loc_1800044B4
0x1800044cf  inc     edx
0x1800044d1  jmp     loc_180004437
0x1800044d6  test    rdx, rdx
0x1800044d9  jz      loc_1800046E3
0x1800044df  test    r13, r13
0x1800044e2  jz      short loc_1800044F0
0x1800044e4  movzx   eax, byte ptr [rdx+1]
0x1800044e8  cmp     eax, [rdi]
0x1800044ea  jnz     loc_180004796
0x1800044f0  movzx   ecx, word ptr [rdx+4]
0x1800044f4  test    cx, cx
0x1800044f7  jz      loc_180004838
0x1800044fd  mov     ebp, ecx
0x1800044ff  cmp     esi, ecx
0x180004501  jb      loc_180004BA6
0x180004507  movzx   r14d, [rsp+0C8h+arg_28]
0x180004510  mov     eax, 10h
0x180004515  test    r14b, r14b
0x180004518  mov     esi, 18h
0x18000451d  mov     r8d, 43646948h
0x180004523  mov     ecx, 40h ; '@'
0x180004528  cmovz   esi, eax
0x18000452b  mov     edx, esi
0x18000452d  call    cs:__imp_ExAllocatePool2
0x180004534  nop     dword ptr [rax+rax+00h]
0x180004539  test    rax, rax
0x18000453c  jz      loc_180004A3A
0x180004542  mov     rcx, [rsp+0C8h+var_40]
0x18000454a  test    r14b, r14b
0x18000454d  mov     [rax+8], ebp
0x180004550  mov     ebp, 0B0263h
0x180004555  mov     [rax], rcx
0x180004558  mov     ecx, 0B000Fh
0x18000455d  mov     [rax+0Ch], r12b
0x180004561  cmovz   ebp, ecx
0x180004564  mov     [rbx+70h], rax
0x180004568  jnz     loc_180004786
0x18000456e  mov     rax, [rbx+0B8h]
0x180004575  lea     rcx, HidpInterruptWriteComplete
0x18000457c  mov     r10, [rsp+0C8h+arg_8]
0x180004584  mov     byte ptr [rax-48h], 0Fh
0x180004588  mov     [rax-30h], ebp
0x18000458b  mov     [rax-38h], esi
0x18000458e  mov     rax, [rbx+0B8h]
0x180004595  mov     [rax-10h], rcx
0x180004599  mov     [rax-8], r10
0x18000459d  mov     byte ptr [rax-45h], 0E0h
0x1800045a1  test    r13, r13
0x1800045a4  jz      short loc_1800045B6
0x1800045a6  mov     rdx, [rdi+88h]
0x1800045ad  test    rdx, rdx
0x1800045b0  jnz     loc_180004AEA
0x1800045b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045bd  lea     rdi, WPP_GLOBAL_Control
0x1800045c4  cmp     rcx, rdi
0x1800045c7  jz      short loc_1800045D4
0x1800045c9  mov     eax, [rcx+2Ch]
0x1800045cc  test    al, al
0x1800045ce  js      loc_180004B0E
0x1800045d4  xor     dl, dl
0x1800045d6  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800045dd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800045e4  setnz   r8b
0x1800045e8  test    dl, dl
0x1800045ea  jnz     short loc_1800045F1
0x1800045ec  test    r8b, r8b
0x1800045ef  jz      short loc_18000462D
0x1800045f1  mov     rax, [r10+30h]
0x1800045f5  mov     r9, [r10+40h]
0x1800045f9  mov     rcx, [rcx+18h]
0x1800045fd  mov     [rsp+0C8h+var_60], ebp
0x180004601  mov     [rsp+0C8h+var_68], r12d
0x180004606  mov     [rsp+0C8h+var_70], rbx
0x18000460b  mov     [rsp+0C8h+var_78], rax
0x180004610  mov     eax, [r10+8]
0x180004614  mov     dword ptr [rsp+0C8h+var_80], eax
0x180004618  mov     rax, [r9+20h]
0x18000461c  mov     r9, [r15+2A0h]
0x180004623  mov     [rsp+0C8h+var_88], rax
0x180004628  call    WPP_RECORDER_AND_TRACE_SF_qdqqdL
0x18000462d  mov     rcx, [r15]
0x180004630  mov     rdx, rbx; BugCheckParameter1
0x180004633  dec     byte ptr [rbx+43h]
0x180004636  movzx   eax, byte ptr [rbx+43h]
0x18000463a  test    al, al
0x18000463c  jle     loc_180004B1F
0x180004642  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x18000464a  mov     rax, [rbx+0B8h]
0x180004651  movzx   r15d, byte ptr [rax]
0x180004655  mov     [rax+28h], rcx
0x180004659  mov     rbp, [rcx+40h]
0x18000465d  mov     rax, [rbp+28h]
0x180004661  mov     rax, [rax+r15*8+20h]
0x180004666  call    _guard_dispatch_icall
0x18000466b  cmp     byte ptr [rbp+18h], 0
0x18000466f  mov     r14d, eax
0x180004672  jnz     loc_18000477D
0x180004678  mov     rcx, cs:WPP_GLOBAL_Control
0x18000467f  cmp     rcx, rdi
0x180004682  jz      short loc_18000468F
0x180004684  mov     eax, [rcx+2Ch]
0x180004687  test    al, 8
0x180004689  jnz     loc_180004B40
0x18000468f  xor     dl, dl
0x180004691  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180004698  jz      short loc_1800046A5
0x18000469a  cmp     word ptr [rcx+48h], 0
0x18000469f  jnz     loc_180004B51
0x1800046a5  xor     r8b, r8b
0x1800046a8  test    dl, dl
0x1800046aa  jnz     loc_180004B59
0x1800046b0  test    r8b, r8b
0x1800046b3  jnz     loc_180004B59
0x1800046b9  mov     rax, [rsp+0C8h+arg_30]
0x1800046c1  mov     byte ptr [rax], 1
0x1800046c4  mov     rbx, [rsp+0C8h+arg_0]
0x1800046cc  mov     eax, r14d
0x1800046cf  add     rsp, 90h
0x1800046d6  pop     r15
0x1800046d8  pop     r14
0x1800046da  pop     r13
0x1800046dc  pop     r12
0x1800046de  pop     rdi
0x1800046df  pop     rsi
0x1800046e0  pop     rbp
0x1800046e1  retn
0x1800046e3  mov     edx, r12d
0x1800046e6  mov     rcx, r15
0x1800046e9  call    TraceLoggingGetReportIdentifierFailed
0x1800046ee  mov     r14d, 0C000000Dh
0x1800046f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046fb  lea     rdi, WPP_GLOBAL_Control
0x180004702  cmp     rcx, rdi
0x180004705  jnz     loc_180004BD1
0x18000470b  xor     dl, dl
0x18000470d  lea     rsi, WPP_RECORDER_INITIALIZED
0x180004714  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18000471b  setnz   r8b
0x18000471f  test    dl, dl
0x180004721  jnz     short loc_180004728
0x180004723  test    r8b, r8b
0x180004726  jz      short loc_1800046C4
0x180004728  mov     rax, [rbp+30h]
0x18000472c  mov     r9, [rbp+40h]
0x180004730  mov     rcx, [rcx+18h]
0x180004734  mov     [rsp+0C8h+var_60], r14d
0x180004739  mov     [rsp+0C8h+var_68], r12d
0x18000473e  mov     [rsp+0C8h+var_70], rbx
0x180004743  mov     [rsp+0C8h+var_78], rax
0x180004748  mov     eax, [rbp+8]
0x18000474b  mov     dword ptr [rsp+0C8h+var_80], eax
0x18000474f  mov     rax, [r9+20h]
0x180004753  mov     r9, [r15+2A0h]
0x18000475a  mov     [rsp+0C8h+var_88], rax
0x18000475f  mov     [rsp+0C8h+var_98], 60h ; '`'
0x180004766  mov     [rsp+0C8h+var_A0], 8
0x18000476e  mov     byte ptr [rsp+0C8h+BugCheckParameter4], 3
0x180004773  call    WPP_RECORDER_AND_TRACE_SF_qdqqdd
0x180004778  jmp     loc_1800046C4
0x18000477d  mov     rbp, [rbp+60h]
0x180004781  jmp     loc_180004678
0x180004786  or      dword ptr [rax+10h], 1
0x18000478a  mov     dword ptr [rax+14h], 0
0x180004791  jmp     loc_18000456E
0x180004796  mov     r14d, 0C0000010h
0x18000479c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047a3  lea     rdi, WPP_GLOBAL_Control
0x1800047aa  cmp     rcx, rdi
0x1800047ad  jnz     loc_180004A1E
0x1800047b3  xor     dl, dl
0x1800047b5  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800047bc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800047c3  setnz   r8b
0x1800047c7  test    dl, dl
0x1800047c9  jnz     short loc_1800047D4
0x1800047cb  test    r8b, r8b
0x1800047ce  jz      loc_1800046C4
0x1800047d4  mov     rax, [rbp+30h]
0x1800047d8  mov     r9, [rbp+40h]
0x1800047dc  mov     rcx, [rcx+18h]
0x1800047e0  mov     [rsp+0C8h+var_60], r14d
0x1800047e5  mov     [rsp+0C8h+var_68], r12d
0x1800047ea  mov     [rsp+0C8h+var_70], rbx
0x1800047ef  mov     [rsp+0C8h+var_78], rax
0x1800047f4  mov     eax, [rsp+0C8h+arg_18]
0x1800047fb  mov     dword ptr [rsp+0C8h+var_80], eax
0x1800047ff  mov     rax, [r9+20h]
0x180004803  mov     r9, [r15+2A0h]
0x18000480a  mov     [rsp+0C8h+var_88], rax
0x18000480f  mov     [rsp+0C8h+var_98], 61h ; 'a'
0x180004816  mov     [rsp+0C8h+var_A0], 8
0x18000481e  mov     byte ptr [rsp+0C8h+BugCheckParameter4], 3
0x180004823  call    WPP_RECORDER_AND_TRACE_SF_qdqqdd
0x180004828  jmp     loc_1800046C4
0x18000482d  mov     r14d, 0C00000E8h
0x180004833  jmp     loc_1800046C4
0x180004838  mov     r14d, 0C000000Dh
0x18000483e  mov     r10, cs:WPP_GLOBAL_Control
0x180004845  lea     rdi, WPP_GLOBAL_Control
0x18000484c  cmp     r10, rdi
0x18000484f  jnz     loc_180004BB3
0x180004855  xor     dl, dl
0x180004857  lea     rsi, WPP_RECORDER_INITIALIZED
0x18000485e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180004865  setnz   r8b
0x180004869  test    dl, dl
0x18000486b  jnz     short loc_180004876
0x18000486d  test    r8b, r8b
0x180004870  jz      loc_1800046C4
0x180004876  mov     r9, [rbp+40h]
0x18000487a  mov     eax, [rsp+0C8h+var_48]
0x180004881  mov     [rsp+0C8h+var_58], eax
0x180004885  mov     rax, [rbp+30h]
0x180004889  mov     word ptr [rsp+0C8h+var_60], cx
0x18000488e  mov     rcx, [r10+18h]
0x180004892  mov     [rsp+0C8h+var_68], r12d
0x180004897  mov     [rsp+0C8h+var_70], rbx
0x18000489c  mov     [rsp+0C8h+var_78], rax
0x1800048a1  mov     eax, [rsp+0C8h+arg_18]
0x1800048a8  mov     dword ptr [rsp+0C8h+var_80], eax
0x1800048ac  mov     rax, [r9+20h]
0x1800048b0  mov     r9, [r15+2A0h]
0x1800048b7  mov     [rsp+0C8h+var_88], rax
0x1800048bc  call    WPP_RECORDER_AND_TRACE_SF_qdqqdHDd
0x1800048c1  jmp     loc_1800046C4
0x1800048c6  mov     edx, r12d
  ... truncated ...
```
