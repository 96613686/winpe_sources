# CBasicQualifierSet::IsValidQualifierSet(void)

- ea: `0x1800136a0`
- end: `0x180013aad`
- name: `?IsValidQualifierSet@CBasicQualifierSet@@QEAAJXZ`
- size: `1037`
- prototype: `__int64 __fastcall(CBasicQualifierSet *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012a50`
- `0x180019c70`

## callees

- `0x1800088d0`
- `0x1800136a0`
- `0x180037120`
- `0x18006fa4c`
- `0x180071c50`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800137f2`
- `wbemcomn!GetMemLogObject` at `0x180013842`
- `wbemcomn!GetMemLogObject` at `0x180013980`
- `wbemcomn!GetMemLogObject` at `0x1800139ab`
- `wbemcomn!GetMemLogObject` at `0x1800139ed`
- `wbemcomn!GetMemLogObject` at `0x1800137f2`
- `wbemcomn!GetMemLogObject` at `0x180013842`
- `wbemcomn!GetMemLogObject` at `0x180013980`
- `wbemcomn!GetMemLogObject` at `0x1800139ab`
- `wbemcomn!GetMemLogObject` at `0x1800139ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013800`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013850`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001398e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800139b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800139fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013800`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013850`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001398e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800139b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800139fb`

## pseudocode

```c
__int64 __fastcall CBasicQualifierSet::IsValidQualifierSet(CBasicQualifierSet *this)
{
  _QWORD *v1; // rax
  _DWORD *v2; // rdi
  _DWORD *v3; // r12
  unsigned __int64 v4; // r14
  int v5; // eax
  _DWORD *v6; // rdx
  char *v7; // rbx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rbp
  __int64 v11; // rsi
  int v12; // r10d
  char *v13; // r9
  unsigned int v14; // ecx
  int v15; // edx
  __int64 v16; // rax
  unsigned int v17; // r11d
  _DWORD *v18; // r8
  int v19; // eax
  unsigned __int64 v20; // rcx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v22; // rcx
  __int64 v23; // rdx
  CMemoryLog *v24; // rax
  _DWORD *v25; // rbx
  unsigned int *v26; // rsi
  int v27; // r13d
  char *v28; // r8
  int v29; // eax
  char *v30; // r13
  int i; // ebx
  __int64 v32; // rax
  CMemoryLog *v33; // rax
  CWbemRefreshingSvc *v34; // rcx
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  __int64 v37; // rdx
  int pExceptionObject; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v39; // [rsp+68h] [rbp+10h]

  v1 = (_QWORD *)*((_QWORD *)this + 2);
  v2 = (_DWORD *)v1[1];
  v3 = v1 + 2;
  v4 = *v1;
  if ( v2 == (_DWORD *)(v1 + 2) )
  {
    v5 = 4;
    v6 = (_DWORD *)(v4 - 4);
  }
  else
  {
    v5 = 12;
    v6 = v2;
  }
  v7 = (char *)*((_QWORD *)this + 1);
  v8 = (unsigned __int64)v6 + (unsigned int)(v5 + *v2);
  v9 = (unsigned __int64)&v7[*(unsigned int *)this - 4];
  while ( (unsigned __int64)v7 < v9 )
  {
    v11 = *(unsigned int *)v7;
    if ( (_DWORD)v11 == -1 )
    {
      v7 += CType::GetLength(*(_DWORD *)(v7 + 5)) + 9;
    }
    else
    {
      if ( !CFastHeap::IsFakeAddress(v11) )
      {
        if ( (unsigned int)v11 > v2[1] )
          throw (CX_Exception *)&pExceptionObject;
        v20 = v4 + v11;
        if ( v4 + v11 )
        {
          if ( v20 < v4 || v20 >= v8 )
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, -2147217407);
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v23 = 17;
              goto LABEL_31;
            }
            return 2147749889LL;
          }
        }
      }
      v12 = *(_DWORD *)(v7 + 5);
      v13 = v7 + 5;
      v14 = v12 & 0xFFF;
      if ( v14 == 8 || v14 == 13 || v14 - 101 <= 1 || (v15 = v12 & 0x2000, (v12 & 0x2000) != 0) )
      {
        v16 = *(unsigned int *)(v7 + 9);
        v17 = v2[1];
        if ( (unsigned int)v16 > v17 )
          throw (CX_Exception *)&pExceptionObject;
        v18 = (_DWORD *)(v4 + v16);
        if ( v4 + v16 < v4 || (unsigned __int64)v18 >= v8 )
        {
          v24 = GetMemLogObject();
          CMemoryLog::Write(v24, -2147217407);
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 2147749889LL;
          }
          v23 = 16;
          goto LABEL_31;
        }
        v15 = v12 & 0x2000;
        if ( (v12 & 0x2000) != 0 )
        {
          v25 = (_DWORD *)(v4 - 4);
          if ( v2 != v3 )
            v25 = v2;
          if ( v14 == 8 || v14 == 13 || v14 - 101 <= 1 )
          {
            v26 = v18 + 1;
            v27 = 4;
            if ( v14 > 0x7F )
              v27 = 0;
            pExceptionObject = *v18;
            v39 = v27;
            v28 = (char *)v26 + v27 * pExceptionObject;
            if ( (unsigned __int64)v28 < v4 )
              goto LABEL_62;
            v29 = 4;
            if ( v2 != v3 )
              v29 = 12;
            v30 = (char *)v25 + (unsigned int)(*v2 + v29);
            if ( v28 > v30 )
            {
LABEL_62:
              v36 = GetMemLogObject();
              CMemoryLog::Write(v36, -2147217407);
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v37 = 34;
LABEL_66:
                WPP_SF_d(*((_QWORD *)v34 + 2), v37, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids, 2147749889LL);
              }
LABEL_58:
              v35 = GetMemLogObject();
              CMemoryLog::Write(v35, -2147217407);
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                return 2147749889LL;
              }
              v23 = 15;
LABEL_31:
              WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749889LL);
              return 2147749889LL;
            }
            for ( i = 0; i < pExceptionObject; ++i )
            {
              v32 = *v26;
              if ( (unsigned int)v32 > v17 )
                throw (CX_Exception *)&pExceptionObject;
              if ( v4 + v32 < v4 || v4 + v32 >= (unsigned __int64)v30 )
              {
                v33 = GetMemLogObject();
                CMemoryLog::Write(v33, -2147217407);
                v34 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v37 = 35;
                  goto LABEL_66;
                }
                goto LABEL_58;
              }
              v26 = (unsigned int *)((char *)v26 + v39);
            }
          }
        }
      }
      if ( v14 > 0x7F )
      {
        v7 = v13 + 4;
      }
      else
      {
        if ( v15 )
          v19 = 4;
        else
          v19 = *((_DWORD *)&m_staticLengths + (v12 & 0xFFF));
        v7 = &v13[v19 + 4];
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800136a0  mov     [rsp+arg_10], rbx
0x1800136a5  push    rbp
0x1800136a6  push    rsi
0x1800136a7  push    rdi
0x1800136a8  push    r12
0x1800136aa  push    r13
0x1800136ac  push    r14
0x1800136ae  push    r15
0x1800136b0  sub     rsp, 20h
0x1800136b4  mov     rax, [rcx+10h]
0x1800136b8  mov     rdi, [rax+8]
0x1800136bc  lea     r12, [rax+10h]
0x1800136c0  mov     r14, [rax]
0x1800136c3  cmp     rdi, r12
0x1800136c6  jnz     short loc_180013727
0x1800136c8  mov     eax, 4
0x1800136cd  lea     rdx, [r14-4]
0x1800136d1  mov     r15d, [rdi]
0x1800136d4  lea     r13, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x1800136db  mov     rbx, [rcx+8]
0x1800136df  add     r15d, eax
0x1800136e2  mov     eax, [rcx]
0x1800136e4  add     r15, rdx
0x1800136e7  lea     rbp, [rbx-4]
0x1800136eb  add     rbp, rax
0x1800136ee  cmp     rbx, rbp
0x1800136f1  jb      short loc_180013731
0x1800136f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136fa  lea     rbx, WPP_GLOBAL_Control
0x180013701  cmp     rcx, rbx
0x180013704  jz      short loc_180013710
0x180013706  test    byte ptr [rcx+1Ch], 1
0x18001370a  jnz     loc_180013A4D
0x180013710  xor     eax, eax
0x180013712  mov     rbx, [rsp+58h+arg_10]
0x180013717  add     rsp, 20h
0x18001371b  pop     r15
0x18001371d  pop     r14
0x18001371f  pop     r13
0x180013721  pop     r12
0x180013723  pop     rdi
0x180013724  pop     rsi
0x180013725  pop     rbp
0x180013726  retn
0x180013727  mov     eax, 0Ch
0x18001372c  mov     rdx, rdi
0x18001372f  jmp     short loc_1800136D1
0x180013731  mov     esi, [rbx]
0x180013733  cmp     esi, 0FFFFFFFFh
0x180013736  jz      loc_180013957
0x18001373c  mov     ecx, esi; unsigned int
0x18001373e  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x180013743  test    al, al
0x180013745  jz      loc_1800137CF
0x18001374b  mov     r10d, [rbx+5]
0x18001374f  lea     r9, [rbx+5]
0x180013753  mov     ecx, r10d
0x180013756  and     ecx, 0FFFh
0x18001375c  cmp     ecx, 8
0x18001375f  jz      short loc_180013779
0x180013761  cmp     ecx, 0Dh
0x180013764  jz      short loc_180013779
0x180013766  lea     eax, [rcx-65h]
0x180013769  cmp     eax, 1
0x18001376c  jbe     short loc_180013779
0x18001376e  mov     edx, r10d
0x180013771  and     edx, 2000h
0x180013777  jz      short loc_1800137AE
0x180013779  mov     eax, [rbx+9]
0x18001377c  mov     r11d, [rdi+4]
0x180013780  cmp     eax, r11d
0x180013783  ja      loc_180013933
0x180013789  lea     r8, [r14+rax]
0x18001378d  cmp     r8, r14
0x180013790  jb      loc_180013842
0x180013796  cmp     r8, r15
0x180013799  jnb     loc_180013842
0x18001379f  mov     edx, r10d
0x1800137a2  and     edx, 2000h
0x1800137a8  jnz     loc_180013877
0x1800137ae  cmp     ecx, 7Fh
0x1800137b1  ja      loc_180013A40
0x1800137b7  test    edx, edx
0x1800137b9  jz      loc_180013916
0x1800137bf  mov     eax, 4
0x1800137c4  lea     ebx, [rax+4]
0x1800137c7  add     rbx, r9
0x1800137ca  jmp     loc_1800136EE
0x1800137cf  cmp     esi, [rdi+4]
0x1800137d2  ja      loc_180013945
0x1800137d8  mov     rcx, rsi
0x1800137db  add     rcx, r14
0x1800137de  jz      loc_18001374B
0x1800137e4  cmp     rcx, r14
0x1800137e7  jb      short loc_1800137F2
0x1800137e9  cmp     rcx, r15
0x1800137ec  jb      loc_18001374B
0x1800137f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800137f8  mov     rcx, rax
0x1800137fb  mov     edx, 80041001h
0x180013800  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013806  mov     rcx, cs:WPP_GLOBAL_Control
0x18001380d  lea     rbx, WPP_GLOBAL_Control
0x180013814  cmp     rcx, rbx
0x180013817  jz      short loc_18001386D
0x180013819  test    byte ptr [rcx+1Ch], 1
0x18001381d  jz      short loc_18001386D
0x18001381f  cmp     byte ptr [rcx+19h], 2
0x180013823  jb      short loc_18001386D
0x180013825  mov     edx, 11h
0x18001382a  mov     rcx, [rcx+10h]
0x18001382e  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180013835  mov     r9d, 80041001h
0x18001383b  call    WPP_SF_d
0x180013840  jmp     short loc_18001386D
0x180013842  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013848  mov     rcx, rax
0x18001384b  mov     edx, 80041001h
0x180013850  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013856  mov     rcx, cs:WPP_GLOBAL_Control
0x18001385d  lea     rbx, WPP_GLOBAL_Control
0x180013864  cmp     rcx, rbx
0x180013867  jnz     loc_180013A8F
0x18001386d  mov     eax, 80041001h
0x180013872  jmp     loc_180013712
0x180013877  lea     rbx, [r14-4]
0x18001387b  cmp     rdi, r12
0x18001387e  jz      short loc_180013883
0x180013880  mov     rbx, rdi
0x180013883  cmp     ecx, 8
0x180013886  jz      short loc_180013899
0x180013888  cmp     ecx, 0Dh
0x18001388b  jz      short loc_180013899
0x18001388d  lea     eax, [rcx-65h]
0x180013890  cmp     eax, 1
0x180013893  ja      loc_1800137AE
0x180013899  xor     eax, eax
0x18001389b  lea     rsi, [r8+4]
0x18001389f  cmp     ecx, 7Fh
0x1800138a2  mov     r13d, 4
0x1800138a8  cmova   r13d, eax
0x1800138ac  mov     eax, [r8]
0x1800138af  mov     [rsp+58h+pExceptionObject], eax
0x1800138b3  imul    eax, r13d
0x1800138b7  mov     [rsp+58h+arg_8], r13d
0x1800138bc  movsxd  r8, eax
0x1800138bf  add     r8, rsi
0x1800138c2  cmp     r8, r14
0x1800138c5  jb      loc_1800139ED
0x1800138cb  cmp     rdi, r12
0x1800138ce  mov     r13d, 0Ch
0x1800138d4  mov     eax, 4
0x1800138d9  cmovnz  eax, r13d
0x1800138dd  add     eax, [rdi]
0x1800138df  mov     r13d, eax
0x1800138e2  add     r13, rbx
0x1800138e5  cmp     r8, r13
0x1800138e8  ja      loc_1800139ED
0x1800138ee  xor     ebx, ebx
0x1800138f0  cmp     ebx, [rsp+58h+pExceptionObject]
0x1800138f4  jge     short loc_180013927
0x1800138f6  mov     eax, [rsi]
0x1800138f8  cmp     eax, r11d
0x1800138fb  ja      short loc_18001396E
0x1800138fd  lea     r8, [r14+rax]
0x180013901  cmp     r8, r14
0x180013904  jb      short loc_180013980
0x180013906  cmp     r8, r13
0x180013909  jnb     short loc_180013980
0x18001390b  mov     eax, [rsp+58h+arg_8]
0x18001390f  add     rsi, rax
0x180013912  inc     ebx
0x180013914  jmp     short loc_1800138F0
0x180013916  and     r10d, 0FFFh
0x18001391d  mov     eax, [r13+r10*4+0]
0x180013922  jmp     loc_1800137C4
0x180013927  lea     r13, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x18001392e  jmp     loc_1800137AE
0x180013933  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001393a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001393f  call    _CxxThrowException_0
0x180013945  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001394c  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180013951  call    _CxxThrowException_0
0x180013957  mov     ecx, [rbx+5]; unsigned int
0x18001395a  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x18001395f  add     eax, 4
0x180013962  add     rbx, 5
0x180013966  add     rbx, rax
0x180013969  jmp     loc_1800136EE
0x18001396e  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180013975  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001397a  call    _CxxThrowException_0
0x180013980  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013986  mov     rcx, rax
0x180013989  mov     edx, 80041001h
0x18001398e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013994  mov     rcx, cs:WPP_GLOBAL_Control
0x18001399b  lea     rbx, WPP_GLOBAL_Control
0x1800139a2  cmp     rcx, rbx
0x1800139a5  jnz     loc_180013A74
0x1800139ab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800139b1  mov     rcx, rax
0x1800139b4  mov     edx, 80041001h
0x1800139b9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800139bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139c6  cmp     rcx, rbx
0x1800139c9  jz      loc_18001386D
0x1800139cf  test    byte ptr [rcx+1Ch], 1
0x1800139d3  jz      loc_18001386D
0x1800139d9  cmp     byte ptr [rcx+19h], 2
0x1800139dd  jb      loc_18001386D
0x1800139e3  mov     edx, 0Fh
0x1800139e8  jmp     loc_18001382A
0x1800139ed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800139f3  mov     rcx, rax
0x1800139f6  mov     edx, 80041001h
0x1800139fb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a08  lea     rbx, WPP_GLOBAL_Control
0x180013a0f  cmp     rcx, rbx
0x180013a12  jz      short loc_1800139AB
0x180013a14  test    byte ptr [rcx+1Ch], 1
0x180013a18  jz      short loc_1800139AB
0x180013a1a  cmp     byte ptr [rcx+19h], 2
0x180013a1e  jb      short loc_1800139AB
0x180013a20  mov     edx, 22h ; '"'
0x180013a25  mov     rcx, [rcx+10h]
0x180013a29  lea     r8, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids
0x180013a30  mov     r9d, 80041001h
0x180013a36  call    WPP_SF_d
0x180013a3b  jmp     loc_1800139AB
0x180013a40  xor     eax, eax
0x180013a42  lea     ebx, [rax+4]
0x180013a45  add     rbx, r9
0x180013a48  jmp     loc_1800136EE
0x180013a4d  cmp     byte ptr [rcx+19h], 2
0x180013a51  jb      loc_180013710
0x180013a57  mov     rcx, [rcx+10h]
0x180013a5b  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180013a62  mov     edx, 12h
0x180013a67  xor     r9d, r9d
0x180013a6a  call    WPP_SF_d
0x180013a6f  jmp     loc_180013710
0x180013a74  test    byte ptr [rcx+1Ch], 1
0x180013a78  jz      loc_1800139AB
0x180013a7e  cmp     byte ptr [rcx+19h], 2
0x180013a82  jb      loc_1800139AB
0x180013a88  mov     edx, 23h ; '#'
0x180013a8d  jmp     short loc_180013A25
0x180013a8f  test    byte ptr [rcx+1Ch], 1
0x180013a93  jz      loc_18001386D
0x180013a99  cmp     byte ptr [rcx+19h], 2
0x180013a9d  jb      loc_18001386D
0x180013aa3  mov     edx, 10h
0x180013aa8  jmp     loc_18001382A
```
