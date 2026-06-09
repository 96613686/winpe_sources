# CExposedStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180015880`
- end: `0x180015b5e`
- name: `?Seek@CExposedStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(CExposedStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015880`
- `0x180015f30`
- `0x180016810`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001599f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001599f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015b53`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015b53`

## pseudocode

```c
__int64 __fastcall CExposedStream::Seek(
        CExposedStream *this,
        union _LARGE_INTEGER a2,
        int a3,
        union _ULARGE_INTEGER *a4)
{
  _QWORD *v4; // r13
  int v10; // esi
  _QWORD *v11; // rcx
  union _LARGE_INTEGER *v12; // rdx
  union _LARGE_INTEGER v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  _QWORD *v16; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v18; // rcx
  bool v19; // zf
  __int64 v20; // rax
  int v21; // r15d
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rcx
  unsigned __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r9
  int v28; // ecx
  int v29; // eax
  __int64 v30; // rax
  int v31; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v32; // [rsp+28h] [rbp-40h]
  __int128 v33; // [rsp+30h] [rbp-38h]

  v4 = (_QWORD *)*((_QWORD *)this + 15);
  v31 = -2147286784;
  v32 = v4;
  v33 = 0;
  if ( a4 )
    a4->QuadPart = 0;
  if ( a3 )
  {
    if ( (unsigned int)(a3 - 1) >= 2 )
    {
      CSafeSem::Release((CSafeSem *)&v31);
      return 2147680257LL;
    }
  }
  else if ( a2.QuadPart < 0 )
  {
    return (unsigned int)-2147287039;
  }
  v30 = *((_QWORD *)this + 8) - *(_QWORD *)&GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data1;
  if ( !v30 )
    v30 = *((_QWORD *)this + 9) - *(_QWORD *)GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data4;
  if ( !v30 )
  {
    v10 = CSafeSem::Take((CSafeSem *)&v31);
    if ( v10 >= 0 )
    {
      if ( (*(_BYTE *)(*((_QWORD *)this + 13) + 20LL) & 0x20) != 0 )
      {
        v10 = -2147286782;
      }
      else
      {
        v11 = (_QWORD *)*((_QWORD *)this + 14);
        v11[4] = v4[2];
        v11[5] = v4[3];
        v11[6] = v4[4];
        v12 = (union _LARGE_INTEGER *)*((_QWORD *)this + 17);
        v13 = v12[2];
        if ( !a3 )
        {
          v13 = a2;
LABEL_10:
          v12[2] = v13;
          if ( a4 )
            *a4 = (union _ULARGE_INTEGER)v13.QuadPart;
          v10 = 0;
          goto LABEL_13;
        }
        v21 = a3 - 1;
        if ( v21 )
        {
          if ( v21 != 1 )
            goto LABEL_10;
          v22 = *((_QWORD *)this + 13);
          if ( (*(_BYTE *)(v22 + 20) & 0x20) != 0 )
          {
            v10 = -2147286782;
          }
          else
          {
            v23 = *(_QWORD *)(v22 + 104);
            if ( v23 )
              v24 = v23 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            else
              v24 = 0;
            if ( *(_DWORD *)v24 == 1381258052 )
            {
              v25 = *(_QWORD *)(v24 + 176);
            }
            else
            {
              v25 = 0;
              if ( *(_DWORD *)v24 == 1381258068 )
                v25 = *(_QWORD *)(v24 + 112);
            }
            if ( a2.QuadPart >= 0 || -a2.QuadPart <= v25 )
            {
              v13.QuadPart = v25 + a2.QuadPart;
              goto LABEL_10;
            }
            v10 = -2147287039;
          }
        }
        else
        {
          if ( a2.QuadPart >= 0 || -a2.QuadPart <= (unsigned __int64)v13.QuadPart )
          {
            v13.QuadPart += a2.QuadPart;
            goto LABEL_10;
          }
          v10 = -2147287039;
        }
      }
    }
LABEL_13:
    v14 = *((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) )
    {
      v15 = v33;
      if ( (_QWORD)v33 )
      {
        v26 = *(_QWORD *)(v33 + 88);
        v27 = *(_QWORD *)(v33 + 96);
        v28 = *(_DWORD *)(v33 + 104);
        *(_QWORD *)(*((_QWORD *)&v33 + 1) + 8LL) = v26;
        *(_QWORD *)(v14 + 16) = v27;
        if ( v26 )
          v29 = *(_DWORD *)(v26 + 16) - 24;
        else
          v29 = 0;
        *(_DWORD *)(v14 + 32) = v29;
        *(_DWORD *)(v14 + 36) = v28;
        *(_QWORD *)NtCurrentTeb()->ReservedForOle = v27;
        *(_QWORD *)(v14 + 24) = v15;
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)&v33 + 1) + 8LL) = 0;
        *(_QWORD *)(v14 + 16) = 0;
        *(_QWORD *)(v14 + 32) = 0;
        *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
        *(_QWORD *)(v14 + 24) = 0;
      }
    }
    if ( v31 >= 0 )
    {
      v16 = v32;
      CurrentThreadId = GetCurrentThreadId();
      v18 = v16[14];
      if ( *(_DWORD *)(v18 + 8) == CurrentThreadId )
      {
        v19 = (*(_DWORD *)(v18 + 4))-- == 1;
        v20 = v16[14];
        if ( v19 )
        {
          *(_DWORD *)(v20 + 8) = 0;
          if ( _InterlockedDecrement((volatile signed __int32 *)v16[14]) >= 0 )
            SetEvent((HANDLE)v16[15]);
        }
        else
        {
          _InterlockedDecrement((volatile signed __int32 *)v20);
        }
      }
    }
    return (unsigned int)v10;
  }
  return (unsigned int)-2147287034;
}

```

## disassembly

```asm
0x180015880  mov     [rsp+arg_10], rbx
0x180015885  push    rbp
0x180015886  push    rdi
0x180015887  push    r13
0x180015889  push    r14
0x18001588b  push    r15
0x18001588d  sub     rsp, 40h
0x180015891  mov     r13, [rcx+78h]
0x180015895  xor     edi, edi
0x180015897  mov     [rsp+68h+var_48], 80030100h
0x18001589f  xorps   xmm0, xmm0
0x1800158a2  mov     [rsp+68h+var_40], r13
0x1800158a7  mov     r14, r9
0x1800158aa  mov     r15d, r8d
0x1800158ad  mov     rbx, rdx
0x1800158b0  mov     rbp, rcx
0x1800158b3  movdqu  [rsp+68h+var_38], xmm0
0x1800158b9  test    r9, r9
0x1800158bc  jz      short loc_1800158C1
0x1800158be  mov     [r9], rdi
0x1800158c1  mov     [rsp+68h+arg_8], rsi
0x1800158c6  mov     eax, r15d
0x1800158c9  test    r15d, r15d
0x1800158cc  jz      loc_180015B08
0x1800158d2  sub     eax, 1
0x1800158d5  jz      loc_180015AD8
0x1800158db  cmp     eax, 1
0x1800158de  jz      loc_180015AD8
0x1800158e4  lea     rcx, [rsp+68h+var_48]; this
0x1800158e9  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x1800158ee  mov     eax, 80030001h
0x1800158f3  jmp     loc_1800159D7
0x1800158f8  lea     rcx, [rsp+68h+var_48]; this
0x1800158fd  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x180015902  mov     esi, eax
0x180015904  test    eax, eax
0x180015906  js      short loc_180015958
0x180015908  mov     rax, [rbp+68h]
0x18001590c  test    byte ptr [rax+14h], 20h
0x180015910  jnz     loc_180015A6C
0x180015916  mov     rax, [r13+10h]
0x18001591a  mov     rcx, [rbp+70h]
0x18001591e  mov     [rcx+20h], rax
0x180015922  mov     rax, [r13+18h]
0x180015926  mov     [rcx+28h], rax
0x18001592a  mov     rax, [r13+20h]
0x18001592e  mov     [rcx+30h], rax
0x180015932  mov     rdx, [rbp+88h]
0x180015939  mov     rax, [rdx+10h]
0x18001593d  test    r15d, r15d
0x180015940  jnz     loc_1800159F9
0x180015946  mov     rax, rbx
0x180015949  mov     [rdx+10h], rax
0x18001594d  test    r14, r14
0x180015950  jnz     loc_1800159F1
0x180015956  mov     esi, edi
0x180015958  mov     rdx, qword ptr [rsp+68h+var_38+8]
0x18001595d  test    rdx, rdx
0x180015960  jz      short loc_180015993
0x180015962  mov     r8, qword ptr [rsp+68h+var_38]
0x180015967  test    r8, r8
0x18001596a  jnz     loc_180015A76
0x180015970  mov     [rdx+8], rdi
0x180015974  mov     [rdx+10h], rdi
0x180015978  mov     [rdx+20h], r8
0x18001597c  mov     rax, gs:30h
0x180015985  mov     rcx, [rax+1758h]
0x18001598c  mov     [rcx], rdi
0x18001598f  mov     [rdx+18h], rdi
0x180015993  cmp     [rsp+68h+var_48], 0
0x180015998  jl      short loc_1800159D5
0x18001599a  mov     rbx, [rsp+68h+var_40]
0x18001599f  call    cs:__imp_GetCurrentThreadId
0x1800159a5  mov     rcx, [rbx+70h]
0x1800159a9  cmp     [rcx+8], eax
0x1800159ac  jnz     short loc_1800159D5
0x1800159ae  sub     dword ptr [rcx+4], 1
0x1800159b2  mov     rax, [rbx+70h]
0x1800159b6  jnz     loc_180015A64
0x1800159bc  mov     [rax+8], edi
0x1800159bf  mov     ecx, 0FFFFFFFFh
0x1800159c4  mov     rax, [rbx+70h]
0x1800159c8  lock xadd [rax], ecx
0x1800159cc  cmp     ecx, 1
0x1800159cf  jns     loc_180015B4F
0x1800159d5  mov     eax, esi
0x1800159d7  mov     rsi, [rsp+68h+arg_8]
0x1800159dc  mov     rbx, [rsp+68h+arg_10]
0x1800159e4  add     rsp, 40h
0x1800159e8  pop     r15
0x1800159ea  pop     r14
0x1800159ec  pop     r13
0x1800159ee  pop     rdi
0x1800159ef  pop     rbp
0x1800159f0  retn
0x1800159f1  mov     [r14], rax
0x1800159f4  jmp     loc_180015956
0x1800159f9  sub     r15d, 1
0x1800159fd  jnz     short loc_180015A10
0x1800159ff  test    rbx, rbx
0x180015a02  js      loc_180015B36
0x180015a08  add     rax, rbx
0x180015a0b  jmp     loc_180015949
0x180015a10  cmp     r15d, 1
0x180015a14  jnz     loc_180015949
0x180015a1a  mov     rax, [rbp+68h]
0x180015a1e  test    byte ptr [rax+14h], 20h
0x180015a22  jnz     loc_180015B17
0x180015a28  mov     r8, [rax+68h]
0x180015a2c  test    r8, r8
0x180015a2f  jz      loc_180015AD0
0x180015a35  mov     rax, gs:30h
0x180015a3e  mov     rcx, [rax+1758h]
0x180015a45  mov     rcx, [rcx]
0x180015a48  add     rcx, r8
0x180015a4b  mov     eax, [rcx]
0x180015a4d  cmp     eax, 52545344h
0x180015a52  jz      short loc_180015ABB
0x180015a54  mov     r8, rdi
0x180015a57  cmp     eax, 52545354h
0x180015a5c  jnz     short loc_180015AC2
0x180015a5e  mov     r8, [rcx+70h]
0x180015a62  jmp     short loc_180015AC2
0x180015a64  lock dec dword ptr [rax]
0x180015a67  jmp     loc_1800159D5
0x180015a6c  mov     esi, 80030102h
0x180015a71  jmp     loc_180015958
0x180015a76  mov     rax, [r8+58h]
0x180015a7a  mov     r9, [r8+60h]
0x180015a7e  mov     ecx, [r8+68h]
0x180015a82  mov     [rdx+8], rax
0x180015a86  mov     [rdx+10h], r9
0x180015a8a  test    rax, rax
0x180015a8d  jz      short loc_180015AB7
0x180015a8f  mov     eax, [rax+10h]
0x180015a92  sub     eax, 18h
0x180015a95  mov     [rdx+20h], eax
0x180015a98  mov     [rdx+24h], ecx
0x180015a9b  mov     rax, gs:30h
0x180015aa4  mov     rcx, [rax+1758h]
0x180015aab  mov     [rcx], r9
0x180015aae  mov     [rdx+18h], r8
0x180015ab2  jmp     loc_180015993
0x180015ab7  mov     eax, edi
0x180015ab9  jmp     short loc_180015A95
0x180015abb  mov     r8, [rcx+0B0h]
0x180015ac2  test    rbx, rbx
0x180015ac5  js      short loc_180015B21
0x180015ac7  lea     rax, [r8+rbx]
0x180015acb  jmp     loc_180015949
0x180015ad0  mov     rcx, rdi
0x180015ad3  jmp     loc_180015A4B
0x180015ad8  test    r15d, r15d
0x180015adb  jz      short loc_180015B08
0x180015add  mov     rax, [rcx+40h]
0x180015ae1  sub     rax, qword ptr cs:_GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data1
0x180015ae8  jnz     short loc_180015AF5
0x180015aea  mov     rax, [rcx+48h]
0x180015aee  sub     rax, qword ptr cs:_GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data4
0x180015af5  test    rax, rax
0x180015af8  jz      loc_1800158F8
0x180015afe  mov     esi, 80030006h
0x180015b03  jmp     loc_1800159D5
0x180015b08  test    rbx, rbx
0x180015b0b  jns     short loc_180015ADD
0x180015b0d  mov     esi, 80030001h
0x180015b12  jmp     loc_1800159D5
0x180015b17  mov     esi, 80030102h
0x180015b1c  jmp     loc_180015958
0x180015b21  mov     rax, rbx
0x180015b24  neg     rax
0x180015b27  cmp     rax, r8
0x180015b2a  jbe     short loc_180015AC7
0x180015b2c  mov     esi, 80030001h
0x180015b31  jmp     loc_180015958
0x180015b36  mov     rcx, rbx
0x180015b39  neg     rcx
0x180015b3c  cmp     rcx, rax
0x180015b3f  jbe     loc_180015A08
0x180015b45  mov     esi, 80030001h
0x180015b4a  jmp     loc_180015958
0x180015b4f  mov     rcx, [rbx+78h]; hEvent
0x180015b53  call    cs:__imp_SetEvent
0x180015b59  jmp     loc_1800159D5
```
