# EtwpMapEventToEventTrace(_TRACELOG_CONTEXT *,void *,_EVENT_TRACE *,ulong,_WMI_BUFFER_HEADER *)

- ea: `0x180012120`
- end: `0x180012635`
- name: `?EtwpMapEventToEventTrace@@YAKPEAU_TRACELOG_CONTEXT@@PEAXPEAU_EVENT_TRACE@@KPEAU_WMI_BUFFER_HEADER@@@Z`
- size: `1301`
- prototype: `unsigned int __usercall@<eax>(struct _TRACELOG_CONTEXT *@<rcx>, void *@<rdx>, struct _EVENT_TRACE *@<r8>, unsigned int@<r9d>, struct _WMI_BUFFER_HEADER *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180005010`
- `0x18000501c`
- `0x1800052b4`
- `0x180005cc8`

## callees

- `0x180001eb2`
- `0x1800109ac`
- `0x180012120`
- `0x18001263c`

## pseudocode

```c
__int64 __fastcall EtwpMapEventToEventTrace(
        struct _TRACELOG_CONTEXT *a1,
        char *a2,
        struct _EVENT_TRACE *a3,
        unsigned int a4,
        struct _WMI_BUFFER_HEADER *a5)
{
  unsigned int v8; // r12d
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  unsigned int v12; // ebp
  unsigned int v13; // ebp
  unsigned int v14; // ebp
  bool v15; // zf
  unsigned int v16; // ebp
  USHORT v17; // dx
  unsigned int v18; // r11d
  ULONG v19; // r10d
  int v20; // r11d
  int v21; // eax
  unsigned int v22; // r8d
  ULONG v23; // ecx
  char *v24; // rax
  unsigned int v25; // r10d
  __int16 v26; // bp
  ULONG *v27; // rcx
  __int64 v28; // r11
  union _LARGE_INTEGER *v29; // r14
  unsigned int LowPart; // eax
  union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F v31; // xmm0
  int v32; // r10d
  ULONG v33; // eax
  unsigned int v34; // r15d
  unsigned int v35; // ebp
  unsigned int v36; // ebp
  unsigned int v37; // ebp
  unsigned int v38; // ebp
  bool v39; // al
  union _LARGE_INTEGER *v40; // rdx
  LARGE_INTEGER *p_TimeStamp; // rcx
  int v42; // ecx
  ULONG Size; // eax
  ULONG v44; // r10d
  int v45; // r15d
  unsigned int v46; // eax
  USHORT v48; // ax

  v8 = 0;
  v10 = 0;
  memset_0(a3, 0, sizeof(struct _EVENT_TRACE));
  if ( a1 )
    v10 = (*((_DWORD *)a1 + 8) & 0x100 | (*((_DWORD *)a1 + 27) >> 2) & 0x200u) >> 8;
  if ( a4 <= 0xF )
  {
    if ( a4 != 15 )
    {
      v11 = a4 - 1;
      if ( v11 && (v12 = v11 - 1) != 0 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v16 = v14 - 6;
            v15 = v16 == 0;
LABEL_53:
            if ( !v15 )
            {
              if ( v16 == 1 && a1 )
              {
                v39 = (*((_DWORD *)a1 + 27) & 0x100) != 0
                   || *((_BYTE *)a1 + 206) > 1u
                   || *((_BYTE *)a1 + 206) == 1 && *((_BYTE *)a1 + 207);
                v40 = (union _LARGE_INTEGER *)(a2 + 16);
                p_TimeStamp = &a3->Header.TimeStamp;
                *(_OWORD *)&a3->Header.Size = *(_OWORD *)a2;
                *(_OWORD *)&a3->Header.TimeStamp.LowPart = *((_OWORD *)a2 + 1);
                *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&a3->Header.24 + 8) = (union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F)*((_OWORD *)a2 + 2);
                if ( v39 )
                {
                  *(_OWORD *)&a3->InstanceId = *((_OWORD *)a2 + 3);
                  *(_QWORD *)a3->ParentGuid.Data4 = *((_QWORD *)a2 + 8);
                  a3->Header.FieldTypeFlags = 0;
                  EtwpCalculateCurrentTime(p_TimeStamp, v40, a1);
                }
                else
                {
                  *(_QWORD *)&a3->InstanceId = *((_QWORD *)a2 + 6);
                  a3->Header.FieldTypeFlags = 0;
                  a3->Header.24 = (union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F)NullGuid;
                  EtwpCalculateCurrentTime(p_TimeStamp, v40, a1);
                  a3->InstanceId = *((_DWORD *)a2 + 8);
                  a3->ParentInstanceId = *((_DWORD *)a2 + 9);
                }
                if ( v10 >= 2 )
                  a3->Header.FieldTypeFlags |= 1u;
                goto LABEL_18;
              }
LABEL_55:
              v8 = 87;
              goto LABEL_92;
            }
            *(_OWORD *)&a3->Header.Size = *(_OWORD *)a2;
            *(_OWORD *)&a3->Header.TimeStamp.LowPart = *((_OWORD *)a2 + 1);
            *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&a3->Header.24 + 8) = (union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F)*((_OWORD *)a2 + 2);
            a3->Header.FieldTypeFlags = 0;
            EtwpCalculateCurrentTime(&a3->Header.TimeStamp, &a3->Header.TimeStamp, a1);
            if ( v10 >= 2 )
              a3->Header.FieldTypeFlags |= 1u;
            if ( (v10 & 1) == 0 )
            {
              v42 = 48;
              if ( a3->Header.Size <= 0x30u )
                goto LABEL_92;
              a3->MofData = a2 + 48;
              Size = a3->Header.Size;
              goto LABEL_73;
            }
            goto LABEL_45;
          }
        }
      }
      else
      {
        v10 |= 8u;
      }
      a3->Header.Size = *((_WORD *)a2 + 2);
      a3->Header.ThreadId = *((_DWORD *)a2 + 2);
      a3->Header.ProcessId = *((_DWORD *)a2 + 3);
      a3->Header.Class.Type = a2[6];
      a3->Header.Class.Version = *(_WORD *)a2;
      a3->Header.Guid = *EtwpPacketToGuid((struct _WMI_TRACE_PACKET *)(a2 + 4));
      if ( v10 < v18 )
      {
        a3->Header.FieldTypeFlags = v17;
      }
      else
      {
        a3->Header.KernelTime = *((_DWORD *)a2 + 6);
        a3->Header.UserTime = *((_DWORD *)a2 + 7);
      }
      EtwpCalculateCurrentTime(&a3->Header.TimeStamp, (union _LARGE_INTEGER *)a2 + 2, a1);
      if ( (*(_DWORD *)a2 & 0x8F00) != 0 )
      {
        v21 = v20 & (*(_DWORD *)a2 >> 12);
        v22 = *(_DWORD *)a2 & 0xF00;
        if ( v22 )
          v21 += 8 * (v22 >> 8);
        v19 += v21;
      }
LABEL_18:
      v23 = a3->Header.Size;
      if ( v19 <= v23 )
      {
        if ( (v10 & 1) != 0 )
        {
LABEL_20:
          a3->MofData = a2;
LABEL_91:
          a3->MofLength = v23;
          goto LABEL_92;
        }
        if ( v23 > v19 )
        {
          v24 = &a2[v19];
          v23 -= v19;
LABEL_90:
          a3->MofData = v24;
          goto LABEL_91;
        }
        goto LABEL_92;
      }
      return 87;
    }
    *(_QWORD *)&a3->Header.Size = *(_QWORD *)a2;
    v25 = *(unsigned __int16 *)a2 - 8;
    if ( v25 > 0xFFD8 )
      goto LABEL_55;
    v26 = *((_WORD *)a2 + 3);
    v27 = (ULONG *)(a2 + 8);
    LODWORD(v28) = 8;
    if ( (v26 & 1) != 0 )
    {
      if ( a1 )
        v10 |= (*((_DWORD *)a1 + 58) & 0xC000) != 0 ? 4 : 0;
      if ( v25 < 4 )
        goto LABEL_44;
      if ( v10 >= 4 )
        a3->InstanceId = *v27;
      v25 -= 4;
      v29 = (union _LARGE_INTEGER *)(a2 + 12);
      a3->Header.FieldTypeFlags |= 4u;
    }
    else
    {
      v29 = (union _LARGE_INTEGER *)(a2 + 8);
    }
    if ( (v26 & 4) != 0 )
    {
      if ( v25 < 4 )
        goto LABEL_44;
      LowPart = v29->LowPart;
      v29 = (union _LARGE_INTEGER *)((char *)v29 + 4);
      v25 -= 4;
      a3->Header.Guid.Data1 = LowPart;
    }
    else if ( (v26 & 2) != 0 )
    {
      if ( v25 < 0x10 )
        goto LABEL_44;
      v31 = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&v29->LowPart;
      v29 += 2;
      v25 -= 16;
      a3->Header.24 = v31;
    }
    if ( (v26 & 8) != 0 )
    {
      if ( v25 < 8 )
        goto LABEL_44;
      EtwpCalculateCurrentTime(&a3->Header.TimeStamp, v29, a1);
      v29 = (union _LARGE_INTEGER *)((char *)v29 + v28);
      v27 = (ULONG *)(a2 + 8);
      v25 = v32 - 8;
    }
    if ( (v26 & 0x20) != 0 && v25 >= (unsigned int)v28 )
    {
      a3->Header.ThreadId = v29->LowPart;
      a3->Header.ProcessId = v29->HighPart;
    }
LABEL_44:
    if ( (v10 & 1) == 0 )
    {
      if ( a3->Header.Size < (unsigned __int16)v28 )
        goto LABEL_92;
      v33 = a3->Header.Size - (_DWORD)v28;
      a3->MofData = v27;
LABEL_74:
      a3->MofLength = v33;
      goto LABEL_92;
    }
LABEL_45:
    v33 = a3->Header.Size;
    a3->MofData = a2;
    goto LABEL_74;
  }
  v34 = 16;
  v35 = a4 - 16;
  if ( v35 )
  {
    v36 = v35 - 1;
    if ( v36 )
    {
      v37 = v36 - 1;
      if ( !v37 || (v38 = v37 - 1) == 0 )
      {
        a3->Header.24 = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)(a2 + 24);
        EtwpCalculateCurrentTime(&a3->Header.TimeStamp, (union _LARGE_INTEGER *)a2 + 2, a1);
        a3->Header.Size = v44;
        a3->Header.Class.Type = a2[45];
        a3->Header.Class.Version = (unsigned __int8)a2[42];
        a3->Header.Class.Level = a2[44];
        a3->Header.ThreadId = *((_DWORD *)a2 + 2);
        a3->Header.ProcessId = *((_DWORD *)a2 + 3);
        a3->Header.KernelTime = *((_DWORD *)a2 + 14);
        a3->Header.UserTime = *((_DWORD *)a2 + 15);
        if ( v10 >= 2 )
          a3->Header.FieldTypeFlags |= 1u;
        if ( (v10 & 1) != 0 )
        {
          a3->MofData = a2;
          a3->MofLength = v44;
          goto LABEL_92;
        }
        v42 = 80;
        if ( (unsigned __int16)v44 <= 0x50u )
          goto LABEL_92;
        a3->MofData = a2 + 80;
        Size = v44;
LABEL_73:
        v33 = Size - v42;
        goto LABEL_74;
      }
      v16 = v38 - 1;
      v15 = v16 == 0;
      goto LABEL_53;
    }
  }
  a3->Header.Size = *((_WORD *)a2 + 2);
  a3->Header.Class.Type = a2[6];
  a3->Header.Class.Version = *(_WORD *)a2;
  a3->Header.Guid = *EtwpPacketToGuid((struct _WMI_TRACE_PACKET *)(a2 + 4));
  EtwpCalculateCurrentTime(&a3->Header.TimeStamp, (union _LARGE_INTEGER *)a2 + 1, a1);
  a3->Header.FieldTypeFlags |= 2u;
  a3->Header.ProcessId = -1;
  a3->Header.ThreadId = -1;
  if ( (*(_DWORD *)a2 & 0x8F00) != 0 )
  {
    v45 = (*(_DWORD *)a2 >> 12) & 8;
    v46 = *(_DWORD *)a2 & 0xF00;
    if ( v46 )
      v45 += 8 * (v46 >> 8);
    v34 = v45 + 16;
  }
  v23 = a3->Header.Size;
  if ( v34 > v23 )
    return 87;
  if ( (v10 & 1) != 0 )
    goto LABEL_20;
  if ( v23 > v34 )
  {
    v24 = &a2[v34];
    v23 -= v34;
    goto LABEL_90;
  }
LABEL_92:
  a3->ClientContext = *((_DWORD *)a5 + 10);
  if ( (*((_BYTE *)a5 + 52) & 0x20) != 0 )
    v48 = *((_WORD *)a5 + 20);
  else
    v48 = *((unsigned __int8 *)a5 + 40);
  a3->BufferContext.ProcessorIndex = v48;
  return v8;
}

```

## disassembly

```asm
0x180012120  push    rbx
0x180012122  push    rbp
0x180012123  push    rsi
0x180012124  push    rdi
0x180012125  push    r12
0x180012127  push    r13
0x180012129  push    r14
0x18001212b  push    r15
0x18001212d  sub     rsp, 28h
0x180012131  mov     rdi, r8
0x180012134  mov     rsi, rdx
0x180012137  mov     r13, rcx
0x18001213a  xor     r12d, r12d
0x18001213d  xor     edx, edx; Val
0x18001213f  mov     rcx, rdi; void *
0x180012142  mov     ebp, r9d
0x180012145  xor     ebx, ebx
0x180012147  lea     r8d, [r12+58h]; Size
0x18001214c  call    memset_0
0x180012151  lea     r14d, [r12+2]
0x180012156  mov     r8d, 100h
0x18001215c  test    r13, r13
0x18001215f  jz      short loc_180012180
0x180012161  mov     ebx, [r13+6Ch]
0x180012165  movzx   edx, r14w
0x180012169  mov     eax, [r13+20h]
0x18001216d  shr     ebx, 2
0x180012170  and     eax, r8d
0x180012173  and     ebx, 200h
0x180012179  or      ebx, eax
0x18001217b  shr     ebx, 8
0x18001217e  jmp     short loc_180012183
0x180012180  mov     edx, r14d
0x180012183  cmp     ebp, 0Fh
0x180012186  ja      loc_180012382
0x18001218c  jz      loc_180012274
0x180012192  mov     r11d, 8
0x180012198  sub     ebp, 1
0x18001219b  jz      short loc_1800121B4
0x18001219d  sub     ebp, 1
0x1800121a0  jz      short loc_1800121B4
0x1800121a2  sub     ebp, 1
0x1800121a5  jz      short loc_1800121B7
0x1800121a7  sub     ebp, 1
0x1800121aa  jz      short loc_1800121B7
0x1800121ac  sub     ebp, 6
0x1800121af  jmp     loc_1800123AF
0x1800121b4  or      ebx, r11d
0x1800121b7  lea     rcx, [rsi+4]; struct _WMI_TRACE_PACKET *
0x1800121bb  movzx   eax, word ptr [rcx]
0x1800121be  mov     [rdi], ax
0x1800121c1  mov     eax, [rsi+8]
0x1800121c4  mov     [rdi+8], eax
0x1800121c7  mov     eax, [rsi+0Ch]
0x1800121ca  mov     [rdi+0Ch], eax
0x1800121cd  mov     al, [rsi+6]
0x1800121d0  mov     [rdi+4], al
0x1800121d3  movzx   eax, word ptr [rsi]
0x1800121d6  mov     [rdi+6], ax
0x1800121da  call    ?EtwpPacketToGuid@@YAPEBU_GUID@@PEAU_WMI_TRACE_PACKET@@@Z; EtwpPacketToGuid(_WMI_TRACE_PACKET *)
0x1800121df  movups  xmm0, xmmword ptr [rax]
0x1800121e2  movdqu  xmmword ptr [rdi+18h], xmm0
0x1800121e7  cmp     ebx, r11d
0x1800121ea  jb      short loc_180012200
0x1800121ec  mov     eax, [rsi+18h]
0x1800121ef  mov     r10d, 20h ; ' '
0x1800121f5  mov     [rdi+28h], eax
0x1800121f8  mov     eax, [rsi+1Ch]
0x1800121fb  mov     [rdi+2Ch], eax
0x1800121fe  jmp     short loc_18001220A
0x180012200  mov     r10d, 18h
0x180012206  mov     [rdi+2], dx
0x18001220a  lea     rdx, [rsi+10h]; union _LARGE_INTEGER *
0x18001220e  mov     r8, r13; struct _TRACELOG_CONTEXT *
0x180012211  lea     rcx, [rdi+10h]; union _LARGE_INTEGER *
0x180012215  call    ?EtwpCalculateCurrentTime@@YAXPEAT_LARGE_INTEGER@@0PEAU_TRACELOG_CONTEXT@@@Z; EtwpCalculateCurrentTime(_LARGE_INTEGER *,_LARGE_INTEGER *,_TRACELOG_CONTEXT *)
0x18001221a  mov     r8d, [rsi]
0x18001221d  test    r8d, 8F00h
0x180012224  jz      short loc_180012243
0x180012226  mov     eax, r8d
0x180012229  shr     eax, 0Ch
0x18001222c  and     eax, r11d
0x18001222f  and     r8d, 0F00h
0x180012236  jz      short loc_180012240
0x180012238  shr     r8d, 8
0x18001223c  lea     eax, [rax+r8*8]
0x180012240  add     r10d, eax
0x180012243  movzx   ecx, word ptr [rdi]
0x180012246  cmp     r10d, ecx
0x180012249  ja      loc_1800125DA
0x18001224f  test    bl, 1
0x180012252  jz      short loc_18001225D
0x180012254  mov     [rdi+48h], rsi
0x180012258  jmp     loc_1800125FC
0x18001225d  cmp     ecx, r10d
0x180012260  jbe     loc_1800125FF
0x180012266  mov     eax, r10d
0x180012269  add     rax, rsi
0x18001226c  sub     ecx, r10d
0x18001226f  jmp     loc_1800125F8
0x180012274  mov     rax, [rsi]
0x180012277  mov     [rdi], rax
0x18001227a  movzx   r10d, word ptr [rsi]
0x18001227e  add     r10d, 0FFFFFFF8h
0x180012282  cmp     r10d, 0FFD8h
0x180012289  ja      loc_1800123BA
0x18001228f  movzx   ebp, word ptr [rsi+6]
0x180012293  lea     rcx, [rsi+8]
0x180012297  mov     edx, 4
0x18001229c  lea     r11d, [rdx+4]
0x1800122a0  test    bpl, 1
0x1800122a4  jz      short loc_1800122DF
0x1800122a6  test    r13, r13
0x1800122a9  jz      short loc_1800122BF
0x1800122ab  mov     eax, [r13+0E8h]
0x1800122b2  and     eax, 0C000h
0x1800122b7  neg     eax
0x1800122b9  sbb     eax, eax
0x1800122bb  and     eax, edx
0x1800122bd  or      ebx, eax
0x1800122bf  cmp     r10d, edx
0x1800122c2  jb      loc_180012358
0x1800122c8  cmp     ebx, edx
0x1800122ca  jb      short loc_1800122D1
0x1800122cc  mov     eax, [rcx]
0x1800122ce  mov     [rdi+30h], eax
0x1800122d1  add     r10d, 0FFFFFFFCh
0x1800122d5  lea     r14, [rcx+4]
0x1800122d9  or      [rdi+2], dx
0x1800122dd  jmp     short loc_1800122E2
0x1800122df  mov     r14, rcx
0x1800122e2  test    dl, bpl
0x1800122e5  jz      short loc_1800122FB
0x1800122e7  cmp     r10d, edx
0x1800122ea  jb      short loc_180012358
0x1800122ec  mov     eax, [r14]
0x1800122ef  add     r14, rdx
0x1800122f2  add     r10d, 0FFFFFFFCh
0x1800122f6  mov     [rdi+18h], eax
0x1800122f9  jmp     short loc_18001231C
0x1800122fb  test    bpl, 2
0x1800122ff  jz      short loc_18001231C
0x180012301  mov     r15d, 10h
0x180012307  cmp     r10d, r15d
0x18001230a  jb      short loc_180012358
0x18001230c  movups  xmm0, xmmword ptr [r14]
0x180012310  add     r14, r15
0x180012313  add     r10d, 0FFFFFFF0h
0x180012317  movdqu  xmmword ptr [rdi+18h], xmm0
0x18001231c  test    r11b, bpl
0x18001231f  jz      short loc_180012340
0x180012321  cmp     r10d, r11d
0x180012324  jb      short loc_180012358
0x180012326  lea     rcx, [rdi+10h]; union _LARGE_INTEGER *
0x18001232a  mov     r8, r13; struct _TRACELOG_CONTEXT *
0x18001232d  mov     rdx, r14; union _LARGE_INTEGER *
0x180012330  call    ?EtwpCalculateCurrentTime@@YAXPEAT_LARGE_INTEGER@@0PEAU_TRACELOG_CONTEXT@@@Z; EtwpCalculateCurrentTime(_LARGE_INTEGER *,_LARGE_INTEGER *,_TRACELOG_CONTEXT *)
0x180012335  add     r14, r11
0x180012338  lea     rcx, [rsi+8]
0x18001233c  add     r10d, 0FFFFFFF8h
0x180012340  test    bpl, 20h
0x180012344  jz      short loc_180012358
0x180012346  cmp     r10d, r11d
0x180012349  jb      short loc_180012358
0x18001234b  mov     eax, [r14]
0x18001234e  mov     [rdi+8], eax
0x180012351  mov     eax, [r14+4]
0x180012355  mov     [rdi+0Ch], eax
0x180012358  test    bl, 1
0x18001235b  jz      short loc_180012369
0x18001235d  movzx   eax, word ptr [rdi]
0x180012360  mov     [rdi+48h], rsi
0x180012364  jmp     loc_1800124D7
0x180012369  cmp     [rdi], r11w
0x18001236d  jb      loc_1800125FF
0x180012373  movzx   eax, word ptr [rdi]
0x180012376  sub     eax, r11d
0x180012379  mov     [rdi+48h], rcx
0x18001237d  jmp     loc_1800124D7
0x180012382  mov     r15d, 10h
0x180012388  sub     ebp, r15d
0x18001238b  jz      loc_180012567
0x180012391  sub     ebp, 1
0x180012394  jz      loc_180012567
0x18001239a  sub     ebp, 1
0x18001239d  jz      loc_1800124DF
0x1800123a3  sub     ebp, 1
0x1800123a6  jz      loc_1800124DF
0x1800123ac  sub     ebp, 1
0x1800123af  jz      loc_18001247E
0x1800123b5  cmp     ebp, 1
0x1800123b8  jz      short loc_1800123C5
0x1800123ba  mov     r12d, 57h ; 'W'
0x1800123c0  jmp     loc_1800125FF
0x1800123c5  test    r13, r13
0x1800123c8  jz      short loc_1800123BA
0x1800123ca  test    [r13+6Ch], r8d
0x1800123ce  jnz     short loc_1800123EA
0x1800123d0  cmp     byte ptr [r13+0CEh], 1
0x1800123d8  ja      short loc_1800123EA
0x1800123da  jnz     short loc_1800123E6
0x1800123dc  cmp     byte ptr [r13+0CFh], 1
0x1800123e4  jnb     short loc_1800123EA
0x1800123e6  xor     al, al
0x1800123e8  jmp     short loc_1800123EC
0x1800123ea  mov     al, 1
0x1800123ec  lea     rdx, [rsi+10h]; union _LARGE_INTEGER *
0x1800123f0  mov     r8, r13; struct _TRACELOG_CONTEXT *
0x1800123f3  lea     rcx, [rdi+10h]; union _LARGE_INTEGER *
0x1800123f7  movups  xmm0, xmmword ptr [rsi]
0x1800123fa  movups  xmmword ptr [rdi], xmm0
0x1800123fd  movups  xmm1, xmmword ptr [rsi+10h]
0x180012401  movups  xmmword ptr [rdi+10h], xmm1
0x180012405  movups  xmm0, xmmword ptr [rsi+20h]
0x180012409  movups  xmmword ptr [rdi+20h], xmm0
0x18001240d  test    al, al
0x18001240f  jz      short loc_180012436
0x180012411  movups  xmm1, xmmword ptr [rsi+30h]
0x180012415  xor     eax, eax
0x180012417  mov     r10d, 48h ; 'H'
0x18001241d  movups  xmmword ptr [rdi+30h], xmm1
0x180012421  movsd   xmm0, qword ptr [rsi+40h]
0x180012426  movsd   qword ptr [rdi+40h], xmm0
0x18001242b  mov     [rdi+2], ax
0x18001242f  call    ?EtwpCalculateCurrentTime@@YAXPEAT_LARGE_INTEGER@@0PEAU_TRACELOG_CONTEXT@@@Z; EtwpCalculateCurrentTime(_LARGE_INTEGER *,_LARGE_INTEGER *,_TRACELOG_CONTEXT *)
0x180012434  jmp     short loc_18001246B
0x180012436  movsd   xmm1, qword ptr [rsi+30h]
0x18001243b  xor     eax, eax
0x18001243d  movsd   qword ptr [rdi+30h], xmm1
0x180012442  mov     r10d, 38h ; '8'
0x180012448  mov     [rdi+2], ax
0x18001244c  movups  xmm0, cs:NullGuid
0x180012453  movdqu  xmmword ptr [rdi+18h], xmm0
0x180012458  call    ?EtwpCalculateCurrentTime@@YAXPEAT_LARGE_INTEGER@@0PEAU_TRACELOG_CONTEXT@@@Z; EtwpCalculateCurrentTime(_LARGE_INTEGER *,_LARGE_INTEGER *,_TRACELOG_CONTEXT *)
0x18001245d  mov     r8d, [rsi+20h]
0x180012461  mov     [rdi+30h], r8d
0x180012465  mov     eax, [rsi+24h]
0x180012468  mov     [rdi+34h], eax
0x18001246b  cmp     ebx, r14d
0x18001246e  jb      loc_180012243
0x180012474  or      word ptr [rdi+2], 1
0x180012479  jmp     loc_180012243
0x18001247e  movups  xmm0, xmmword ptr [rsi]
0x180012481  lea     rcx, [rdi+10h]; union _LARGE_INTEGER *
0x180012485  xor     eax, eax
0x180012487  mov     r8, r13; struct _TRACELOG_CONTEXT *
0x18001248a  mov     rdx, rcx; union _LARGE_INTEGER *
0x18001248d  movups  xmmword ptr [rdi], xmm0
0x180012490  movups  xmm1, xmmword ptr [rsi+10h]
0x180012494  movups  xmmword ptr [rdi+10h], xmm1
0x180012498  movups  xmm0, xmmword ptr [rsi+20h]
0x18001249c  movups  xmmword ptr [rdi+20h], xmm0
0x1800124a0  mov     [rdi+2], ax
0x1800124a4  call    ?EtwpCalculateCurrentTime@@YAXPEAT_LARGE_INTEGER@@0PEAU_TRACELOG_CONTEXT@@@Z; EtwpCalculateCurrentTime(_LARGE_INTEGER *,_LARGE_INTEGER *,_TRACELOG_CONTEXT *)
0x1800124a9  cmp     ebx, r14d
0x1800124ac  jb      short loc_1800124B3
0x1800124ae  or      word ptr [rdi+2], 1
0x1800124b3  test    bl, 1
0x1800124b6  jnz     loc_18001235D
0x1800124bc  mov     ecx, 30h ; '0'
0x1800124c1  cmp     [rdi], cx
0x1800124c4  jbe     loc_1800125FF
0x1800124ca  lea     rax, [rsi+30h]
0x1800124ce  mov     [rdi+48h], rax
0x1800124d2  movzx   eax, word ptr [rdi]
0x1800124d5  sub     eax, ecx
0x1800124d7  mov     [rdi+50h], eax
0x1800124da  jmp     loc_1800125FF
0x1800124df  movups  xmm0, xmmword ptr [rsi+18h]
0x1800124e3  movzx   r10d, word ptr [rsi]
0x1800124e7  lea     rdx, [rsi+10h]; union _LARGE_INTEGER *
0x1800124eb  lea     rcx, [rdi+10h]; union _LARGE_INTEGER *
0x1800124ef  mov     r8, r13; struct _TRACELOG_CONTEXT *
0x1800124f2  movdqu  xmmword ptr [rdi+18h], xmm0
0x1800124f7  call    ?EtwpCalculateCurrentTime@@YAXPEAT_LARGE_INTEGER@@0PEAU_TRACELOG_CONTEXT@@@Z; EtwpCalculateCurrentTime(_LARGE_INTEGER *,_LARGE_INTEGER *,_TRACELOG_CONTEXT *)
0x1800124fc  mov     [rdi], r10w
0x180012500  mov     al, [rsi+2Dh]
0x180012503  mov     [rdi+4], al
0x180012506  movzx   eax, byte ptr [rsi+2Ah]
0x18001250a  mov     [rdi+6], ax
0x18001250e  mov     al, [rsi+2Ch]
0x180012511  mov     [rdi+5], al
0x180012514  mov     eax, [rsi+8]
0x180012517  mov     [rdi+8], eax
0x18001251a  mov     eax, [rsi+0Ch]
0x18001251d  mov     [rdi+0Ch], eax
0x180012520  mov     eax, [rsi+38h]
0x180012523  mov     [rdi+28h], eax
0x180012526  mov     eax, [rsi+3Ch]
0x180012529  mov     [rdi+2Ch], eax
0x18001252c  cmp     ebx, r14d
0x18001252f  jb      short loc_180012536
0x180012531  or      word ptr [rdi+2], 1
0x180012536  test    bl, 1
0x180012539  jz      short loc_180012548
0x18001253b  mov     [rdi+48h], rsi
0x18001253f  mov     [rdi+50h], r10d
0x180012543  jmp     loc_1800125FF
0x180012548  mov     ecx, 50h ; 'P'
0x18001254d  cmp     r10w, cx
  ... truncated ...
```
