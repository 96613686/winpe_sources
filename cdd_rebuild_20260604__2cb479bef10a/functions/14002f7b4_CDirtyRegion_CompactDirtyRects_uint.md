# CDirtyRegion::CompactDirtyRects(uint)

- ea: `0x14002f7b4`
- end: `0x14002fa82`
- name: `?CompactDirtyRects@CDirtyRegion@@IEAAXI@Z`
- size: `718`
- prototype: `void __fastcall(CDirtyRegion *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400133d0`
- `0x140013a50`

## callees

- `0x14002f7b4`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002f7f4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002f843`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002f7f4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002f843`
- `watchdog!WdLogSingleEntry0` at `0x14002f7dd`
- `watchdog!WdLogSingleEntry0` at `0x14002f82c`
- `watchdog!WdLogSingleEntry0` at `0x14002f7dd`
- `watchdog!WdLogSingleEntry0` at `0x14002f82c`

## pseudocode

```c
void __fastcall CDirtyRegion::CompactDirtyRects(CDirtyRegion *this, unsigned int a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  unsigned int v6; // r9d
  int v7; // r13d
  int v8; // r8d
  char *v9; // rsi
  int v10; // ecx
  char *v11; // r14
  int v12; // r12d
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // r15d
  int v17; // r11d
  int v18; // ebp
  int v19; // eax
  int v20; // ecx
  int v21; // r10d
  int v22; // edx
  int v23; // ecx
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax

  if ( *((_DWORD *)this + 64) != 16 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2808;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 2808;
  }
  if ( a2 >= *((_DWORD *)this + 64) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2809;
    v5 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v5[3] = gCddImageInfo;
    v5[4] = (unsigned int)dword_14003E570;
    v5[5] = 215857758;
    WdLogGlobalForLineNumber = 2809;
    goto LABEL_55;
  }
  do
  {
    v6 = 0;
    v7 = 0;
    if ( a2 )
    {
      while ( 1 )
      {
        if ( v7 )
        {
LABEL_53:
          v24 = *((_DWORD *)this + 64) - 1;
          *((_DWORD *)this + 64) = v24;
          v25 = 2LL * v24;
          v26 = 2LL * a2;
          a2 = v6;
          *(_OWORD *)((char *)this + 8 * v26) = *(_OWORD *)((char *)this + 8 * v25);
          goto LABEL_55;
        }
        v8 = *((_DWORD *)this + 4 * v6);
        v9 = (char *)this + 16 * v6;
        v10 = *((_DWORD *)this + 4 * a2);
        v11 = (char *)this + 16 * a2;
        v12 = v8;
        if ( v10 != v8 || *((_DWORD *)v11 + 2) != *((_DWORD *)v9 + 2) )
        {
          v16 = *((_DWORD *)this + 4 * a2 + 1);
          v17 = *((_DWORD *)this + 4 * a2);
          v18 = *((_DWORD *)this + 4 * v6 + 1);
          if ( v16 != v18 )
          {
            v12 = *((_DWORD *)this + 4 * v6);
LABEL_30:
            if ( v10 < v8 )
            {
              v17 = *((_DWORD *)this + 4 * a2);
            }
            else
            {
              v21 = *((_DWORD *)v9 + 2);
              if ( *((_DWORD *)v11 + 2) <= v21 && v16 >= v18 )
              {
                v22 = *((_DWORD *)this + 4 * v6 + 3);
                if ( *((_DWORD *)this + 4 * a2 + 3) <= v22 )
                  goto LABEL_41;
              }
            }
            if ( v8 < v10
              || (v21 = *((_DWORD *)this + 4 * v6 + 2), v21 > *((_DWORD *)this + 4 * a2 + 2))
              || v18 < v16
              || (v22 = *((_DWORD *)this + 4 * v6 + 3), v22 > *((_DWORD *)this + 4 * a2 + 3)) )
            {
LABEL_50:
              ++v6;
              goto LABEL_51;
            }
            if ( v10 >= v8 )
LABEL_41:
              v17 = v12;
            *((_DWORD *)this + 4 * v6) = v17;
            v23 = *((_DWORD *)this + 4 * a2 + 2);
            if ( v23 <= v21 )
              v23 = v21;
            *((_DWORD *)this + 4 * v6 + 2) = v23;
            if ( *((_DWORD *)this + 4 * a2 + 1) < v18 )
              v18 = *((_DWORD *)this + 4 * a2 + 1);
            *((_DWORD *)this + 4 * v6 + 1) = v18;
            if ( *((_DWORD *)this + 4 * a2 + 3) > v22 )
              v22 = *((_DWORD *)this + 4 * a2 + 3);
            *((_DWORD *)this + 4 * v6 + 3) = v22;
            goto LABEL_49;
          }
          if ( *((_DWORD *)this + 4 * a2 + 3) != *((_DWORD *)this + 4 * v6 + 3) )
            goto LABEL_30;
          if ( v8 > v10 )
          {
LABEL_23:
            if ( v8 > *((_DWORD *)v11 + 2) )
              goto LABEL_50;
          }
          else if ( v10 > *((_DWORD *)v9 + 2) )
          {
            if ( v8 < v10 )
              goto LABEL_50;
            goto LABEL_23;
          }
          v19 = *((_DWORD *)v9 + 2);
          if ( v10 < v8 )
            v12 = *((_DWORD *)this + 4 * a2);
          *((_DWORD *)this + 4 * v6) = v12;
          v20 = *((_DWORD *)v11 + 2);
          if ( v20 <= v19 )
            v20 = v19;
          *((_DWORD *)this + 4 * v6 + 2) = v20;
          goto LABEL_49;
        }
        v13 = *((_DWORD *)this + 4 * a2 + 1);
        v14 = *((_DWORD *)this + 4 * v6 + 1);
        if ( v14 > v13 )
          goto LABEL_12;
        if ( v13 > *((_DWORD *)this + 4 * v6 + 3) )
          break;
LABEL_13:
        if ( v13 < v14 )
          v14 = *((_DWORD *)this + 4 * a2 + 1);
        *((_DWORD *)this + 4 * v6 + 1) = v14;
        v15 = *((_DWORD *)this + 4 * a2 + 3);
        if ( v15 <= *((_DWORD *)this + 4 * v6 + 3) )
          v15 = *((_DWORD *)this + 4 * v6 + 3);
        *((_DWORD *)this + 4 * v6 + 3) = v15;
LABEL_49:
        v7 = 1;
LABEL_51:
        if ( v6 >= a2 )
        {
          if ( !v7 )
            goto LABEL_54;
          goto LABEL_53;
        }
      }
      if ( v14 < v13 )
        goto LABEL_50;
LABEL_12:
      if ( v14 > *((_DWORD *)this + 4 * a2 + 3) )
        goto LABEL_50;
      goto LABEL_13;
    }
LABEL_54:
    ++a2;
LABEL_55:
    ;
  }
  while ( a2 < *((_DWORD *)this + 64) );
}

```

## disassembly

```asm
0x14002f7b4  push    rbx
0x14002f7b6  push    rbp
0x14002f7b7  push    rsi
0x14002f7b8  push    rdi
0x14002f7b9  push    r12
0x14002f7bb  push    r13
0x14002f7bd  push    r14
0x14002f7bf  push    r15
0x14002f7c1  sub     rsp, 28h
0x14002f7c5  cmp     dword ptr [rcx+100h], 10h
0x14002f7cc  mov     edi, edx
0x14002f7ce  mov     rbx, rcx
0x14002f7d1  mov     ebp, 0CDDBA5Eh
0x14002f7d6  jz      short loc_14002F81F
0x14002f7d8  mov     ecx, 1
0x14002f7dd  call    cs:__imp_WdLogSingleEntry0
0x14002f7e4  nop     dword ptr [rax+rax+00h]
0x14002f7e9  mov     esi, 0AF8h
0x14002f7ee  mov     cs:WdLogGlobalForLineNumber, esi
0x14002f7f4  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002f7fb  nop     dword ptr [rax+rax+00h]
0x14002f800  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002f807  mov     [rax+18h], rcx
0x14002f80b  mov     ecx, cs:dword_14003E570
0x14002f811  mov     [rax+20h], rcx
0x14002f815  mov     [rax+28h], rbp
0x14002f819  mov     cs:WdLogGlobalForLineNumber, esi
0x14002f81f  cmp     edi, [rbx+100h]
0x14002f825  jb      short loc_14002F873
0x14002f827  mov     ecx, 1
0x14002f82c  call    cs:__imp_WdLogSingleEntry0
0x14002f833  nop     dword ptr [rax+rax+00h]
0x14002f838  mov     esi, 0AF9h
0x14002f83d  mov     cs:WdLogGlobalForLineNumber, esi
0x14002f843  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002f84a  nop     dword ptr [rax+rax+00h]
0x14002f84f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002f856  mov     [rax+18h], rcx
0x14002f85a  mov     ecx, cs:dword_14003E570
0x14002f860  mov     [rax+20h], rcx
0x14002f864  mov     [rax+28h], rbp
0x14002f868  mov     cs:WdLogGlobalForLineNumber, esi
0x14002f86e  jmp     loc_14002FA64
0x14002f873  xor     r9d, r9d
0x14002f876  xor     r13d, r13d
0x14002f879  test    edi, edi
0x14002f87b  jz      loc_14002FA62
0x14002f881  test    r13d, r13d
0x14002f884  jnz     loc_14002FA3C
0x14002f88a  mov     edx, r9d
0x14002f88d  add     rdx, rdx
0x14002f890  mov     r10d, edi
0x14002f893  add     r10, r10
0x14002f896  mov     r8d, [rbx+rdx*8]
0x14002f89a  lea     rsi, [rbx+rdx*8]
0x14002f89e  mov     ecx, [rbx+r10*8]
0x14002f8a2  lea     r14, [rbx+r10*8]
0x14002f8a6  mov     r12d, r8d
0x14002f8a9  cmp     ecx, r8d
0x14002f8ac  jnz     short loc_14002F8FD
0x14002f8ae  mov     eax, [rsi+8]
0x14002f8b1  cmp     [r14+8], eax
0x14002f8b5  jnz     short loc_14002F8FD
0x14002f8b7  mov     ecx, [rbx+r10*8+4]
0x14002f8bc  mov     eax, [rbx+rdx*8+4]
0x14002f8c0  cmp     eax, ecx
0x14002f8c2  jg      short loc_14002F8D2
0x14002f8c4  cmp     ecx, [rbx+rdx*8+0Ch]
0x14002f8c8  jle     short loc_14002F8DD
0x14002f8ca  cmp     eax, ecx
0x14002f8cc  jl      loc_14002FA2B
0x14002f8d2  cmp     eax, [rbx+r10*8+0Ch]
0x14002f8d7  jg      loc_14002FA2B
0x14002f8dd  cmp     ecx, eax
0x14002f8df  cmovl   eax, ecx
0x14002f8e2  mov     [rbx+rdx*8+4], eax
0x14002f8e6  mov     ecx, [rbx+r10*8+0Ch]
0x14002f8eb  mov     eax, [rbx+rdx*8+0Ch]
0x14002f8ef  cmp     ecx, eax
0x14002f8f1  cmovle  ecx, eax
0x14002f8f4  mov     [rbx+rdx*8+0Ch], ecx
0x14002f8f8  jmp     loc_14002FA23
0x14002f8fd  mov     r15d, [rbx+r10*8+4]
0x14002f902  mov     r11d, ecx
0x14002f905  mov     ebp, [rbx+rdx*8+4]
0x14002f909  cmp     r15d, ebp
0x14002f90c  jnz     short loc_14002F95C
0x14002f90e  mov     eax, [rbx+rdx*8+0Ch]
0x14002f912  cmp     [rbx+r10*8+0Ch], eax
0x14002f917  jnz     short loc_14002F95F
0x14002f919  cmp     r8d, ecx
0x14002f91c  jg      short loc_14002F92C
0x14002f91e  cmp     ecx, [rsi+8]
0x14002f921  jle     short loc_14002F936
0x14002f923  cmp     r8d, ecx
0x14002f926  jl      loc_14002FA2B
0x14002f92c  cmp     r8d, [r14+8]
0x14002f930  jg      loc_14002FA2B
0x14002f936  mov     eax, [rsi+8]
0x14002f939  cmp     ecx, r8d
0x14002f93c  cmovl   r12d, ecx
0x14002f940  mov     [rbx+rdx*8], r12d
0x14002f944  mov     ecx, [r14+8]
0x14002f948  cmp     ecx, eax
0x14002f94a  cmovle  ecx, eax
0x14002f94d  mov     eax, r9d
0x14002f950  add     rax, rax
0x14002f953  mov     [rbx+rax*8+8], ecx
0x14002f957  jmp     loc_14002FA23
0x14002f95c  mov     r12d, r8d
0x14002f95f  cmp     ecx, r8d
0x14002f962  jl      short loc_14002F98A
0x14002f964  mov     r10d, [rsi+8]
0x14002f968  cmp     [r14+8], r10d
0x14002f96c  jg      short loc_14002F98D
0x14002f96e  cmp     r15d, ebp
0x14002f971  jl      short loc_14002F98D
0x14002f973  mov     eax, r9d
0x14002f976  add     rax, rax
0x14002f979  mov     edx, [rbx+rax*8+0Ch]
0x14002f97d  mov     eax, edi
0x14002f97f  add     rax, rax
0x14002f982  cmp     [rbx+rax*8+0Ch], edx
0x14002f986  jg      short loc_14002F98D
0x14002f988  jmp     short loc_14002F9CC
0x14002f98a  mov     r11d, ecx
0x14002f98d  cmp     r8d, ecx
0x14002f990  jl      loc_14002FA2B
0x14002f996  mov     eax, r9d
0x14002f999  add     rax, rax
0x14002f99c  mov     r10d, [rbx+rax*8+8]
0x14002f9a1  mov     eax, edi
0x14002f9a3  add     rax, rax
0x14002f9a6  cmp     r10d, [rbx+rax*8+8]
0x14002f9ab  jg      short loc_14002FA2B
0x14002f9ad  cmp     ebp, r15d
0x14002f9b0  jl      short loc_14002FA2B
0x14002f9b2  mov     eax, r9d
0x14002f9b5  add     rax, rax
0x14002f9b8  mov     edx, [rbx+rax*8+0Ch]
0x14002f9bc  mov     eax, edi
0x14002f9be  add     rax, rax
0x14002f9c1  cmp     edx, [rbx+rax*8+0Ch]
0x14002f9c5  jg      short loc_14002FA2B
0x14002f9c7  cmp     ecx, r8d
0x14002f9ca  jl      short loc_14002F9CF
0x14002f9cc  mov     r11d, r12d
0x14002f9cf  mov     eax, r9d
0x14002f9d2  add     rax, rax
0x14002f9d5  mov     [rbx+rax*8], r11d
0x14002f9d9  mov     eax, edi
0x14002f9db  add     rax, rax
0x14002f9de  mov     ecx, [rbx+rax*8+8]
0x14002f9e2  cmp     ecx, r10d
0x14002f9e5  mov     eax, r9d
0x14002f9e8  cmovle  ecx, r10d
0x14002f9ec  add     rax, rax
0x14002f9ef  mov     [rbx+rax*8+8], ecx
0x14002f9f3  mov     eax, edi
0x14002f9f5  add     rax, rax
0x14002f9f8  mov     ecx, [rbx+rax*8+4]
0x14002f9fc  cmp     ecx, ebp
0x14002f9fe  mov     eax, r9d
0x14002fa01  cmovl   ebp, ecx
0x14002fa04  add     rax, rax
0x14002fa07  mov     [rbx+rax*8+4], ebp
0x14002fa0b  mov     eax, edi
0x14002fa0d  add     rax, rax
0x14002fa10  mov     ecx, [rbx+rax*8+0Ch]
0x14002fa14  cmp     ecx, edx
0x14002fa16  mov     eax, r9d
0x14002fa19  cmovg   edx, ecx
0x14002fa1c  add     rax, rax
0x14002fa1f  mov     [rbx+rax*8+0Ch], edx
0x14002fa23  mov     r13d, 1
0x14002fa29  jmp     short loc_14002FA2E
0x14002fa2b  inc     r9d
0x14002fa2e  cmp     r9d, edi
0x14002fa31  jb      loc_14002F881
0x14002fa37  test    r13d, r13d
0x14002fa3a  jz      short loc_14002FA62
0x14002fa3c  mov     eax, [rbx+100h]
0x14002fa42  dec     eax
0x14002fa44  mov     [rbx+100h], eax
0x14002fa4a  mov     ecx, eax
0x14002fa4c  add     rcx, rcx
0x14002fa4f  mov     eax, edi
0x14002fa51  add     rax, rax
0x14002fa54  mov     edi, r9d
0x14002fa57  movups  xmm0, xmmword ptr [rbx+rcx*8]
0x14002fa5b  movdqu  xmmword ptr [rbx+rax*8], xmm0
0x14002fa60  jmp     short loc_14002FA64
0x14002fa62  inc     edi
0x14002fa64  cmp     edi, [rbx+100h]
0x14002fa6a  jb      loc_14002F873
0x14002fa70  add     rsp, 28h
0x14002fa74  pop     r15
0x14002fa76  pop     r14
0x14002fa78  pop     r13
0x14002fa7a  pop     r12
0x14002fa7c  pop     rdi
0x14002fa7d  pop     rsi
0x14002fa7e  pop     rbp
0x14002fa7f  pop     rbx
0x14002fa80  retn
```
