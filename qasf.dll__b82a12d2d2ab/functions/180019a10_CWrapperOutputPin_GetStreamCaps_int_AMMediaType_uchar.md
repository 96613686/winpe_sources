# CWrapperOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)

- ea: `0x180019a10`
- end: `0x180019c55`
- name: `?GetStreamCaps@CWrapperOutputPin@@UEAAJHPEAPEAU_AMMediaType@@PEAE@Z`
- size: `581`
- prototype: `int(CWrapperOutputPin *__hidden this, int, struct _AMMediaType **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180001460`
- `0x180001cfc`
- `0x180019a10`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180019ad8`
- `ole32!CoTaskMemAlloc` at `0x180019ad8`
- `ole32!CoTaskMemFree` at `0x180019b1c`
- `ole32!CoTaskMemFree` at `0x180019b1c`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::GetStreamCaps(CWrapperOutputPin *this, int a2, LPVOID *a3, GUID *a4)
{
  __int64 result; // rax
  char *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // r9
  unsigned int v13; // ebx
  struct _AMMediaType *v14; // rax
  unsigned int v15; // esi
  __int64 v16; // rcx
  BYTE *v17; // rcx
  BYTE *v18; // rdx
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 < 0 )
    return 2147942487LL;
  if ( !a4 || !a3 )
    return 2147500035LL;
  v9 = (char *)this - 232;
  if ( *((_BYTE *)this + 191) )
  {
    v10 = *((_QWORD *)this - 19);
    v11 = 0;
    v12 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(v10 + 160);
    v19 = 0;
    if ( v12 )
    {
      (**v12)(v12, &IID_IAMStreamConfig, &v19);
      v11 = v19;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, GUID *))(*(_QWORD *)v11 + 48LL))(
            v11,
            (unsigned int)a2,
            a3,
            a4);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return v13;
  }
  else
  {
    v14 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
    *a3 = v14;
    if ( v14 )
    {
      memset_0(v14, 0, sizeof(struct _AMMediaType));
      v15 = (*(__int64 (__fastcall **)(char *, _QWORD, LPVOID))(*(_QWORD *)v9 + 104LL))(v9, (unsigned int)a2, *a3);
      if ( v15 )
      {
        CoTaskMemFree(*a3);
        *a3 = 0;
        result = 1;
        if ( v15 != -2147220986 && v15 != -2147024809 )
          return v15;
      }
      else
      {
        v16 = *((_QWORD *)this - 19);
        if ( *(_QWORD *)(v16 + 424) == *(_QWORD *)&DMOCATEGORY_VIDEO_ENCODER.Data1
          && *(_QWORD *)(v16 + 432) == *(_QWORD *)DMOCATEGORY_VIDEO_ENCODER.Data4 )
        {
          memset_0(a4, 0, 0x80u);
          *a4 = MEDIATYPE_Video;
          v17 = (BYTE *)*((_QWORD *)*a3 + 10);
          if ( v17 && *((_DWORD *)*a3 + 18) )
          {
            *(_DWORD *)&a4[1].Data2 = *((_DWORD *)v17 + 13);
            *(_DWORD *)a4[1].Data4 = *((_DWORD *)v17 + 14);
            *(_DWORD *)&a4[1].Data4[4] = *((_DWORD *)v17 + 13);
            a4[2].Data1 = *((_DWORD *)v17 + 14);
            *(_DWORD *)&a4[2].Data2 = *((_DWORD *)v17 + 13);
            *(_DWORD *)a4[2].Data4 = *((_DWORD *)v17 + 14);
          }
        }
        else
        {
          *a4 = 0;
          a4[1] = 0;
          a4[2] = 0;
          a4[3].Data1 = 0;
          *a4 = MEDIATYPE_Audio;
          v18 = (BYTE *)*((_QWORD *)*a3 + 10);
          if ( v18 && *((_DWORD *)*a3 + 18) )
          {
            a4[1].Data1 = *((unsigned __int16 *)v18 + 1);
            *(_DWORD *)&a4[1].Data2 = *((unsigned __int16 *)v18 + 1);
            *(_DWORD *)a4[1].Data4 = 1;
            *(_DWORD *)&a4[1].Data4[4] = *((unsigned __int16 *)v18 + 7);
            a4[2].Data1 = *((unsigned __int16 *)v18 + 7);
            *(_DWORD *)&a4[2].Data2 = 8;
            *(_DWORD *)a4[2].Data4 = *((_DWORD *)v18 + 1);
            *(_DWORD *)&a4[2].Data4[4] = *((_DWORD *)v18 + 1);
            a4[3].Data1 = 1;
          }
        }
        return 0;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019a10  push    rbx
0x180019a12  push    rbp
0x180019a13  push    rsi
0x180019a14  push    rdi
0x180019a15  push    r14
0x180019a17  sub     rsp, 40h
0x180019a1b  mov     rax, cs:__security_cookie
0x180019a22  xor     rax, rsp
0x180019a25  mov     [rsp+68h+var_30], rax
0x180019a2a  mov     rbx, r9
0x180019a2d  mov     rdi, r8
0x180019a30  mov     r14d, edx
0x180019a33  mov     rbp, rcx
0x180019a36  test    edx, edx
0x180019a38  jns     short loc_180019A44
0x180019a3a  mov     eax, 80070057h
0x180019a3f  jmp     loc_180019C3D
0x180019a44  test    rbx, rbx
0x180019a47  jz      loc_180019C38
0x180019a4d  test    rdi, rdi
0x180019a50  jz      loc_180019C38
0x180019a56  lea     rsi, [rcx-0E8h]
0x180019a5d  cmp     byte ptr [rsi+1A7h], 0
0x180019a64  jz      short loc_180019AD3
0x180019a66  mov     rax, [rcx-98h]
0x180019a6d  xor     ecx, ecx
0x180019a6f  mov     r9, [rax+0A0h]
0x180019a76  mov     [rsp+68h+var_38], rcx
0x180019a7b  test    r9, r9
0x180019a7e  jz      short loc_180019A9F
0x180019a80  mov     rax, [r9]
0x180019a83  lea     r8, [rsp+68h+var_38]
0x180019a88  lea     rdx, IID_IAMStreamConfig
0x180019a8f  mov     rcx, r9
0x180019a92  mov     rax, [rax]
0x180019a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a9a  mov     rcx, [rsp+68h+var_38]
0x180019a9f  mov     rax, [rcx]
0x180019aa2  mov     r9, rbx
0x180019aa5  mov     r8, rdi
0x180019aa8  mov     edx, r14d
0x180019aab  mov     rax, [rax+30h]
0x180019aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ab4  mov     rcx, [rsp+68h+var_38]
0x180019ab9  mov     ebx, eax
0x180019abb  test    rcx, rcx
0x180019abe  jz      short loc_180019ACC
0x180019ac0  mov     rdx, [rcx]
0x180019ac3  mov     rax, [rdx+10h]
0x180019ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019acc  mov     eax, ebx
0x180019ace  jmp     loc_180019C3D
0x180019ad3  mov     ecx, 58h ; 'X'; cb
0x180019ad8  call    cs:__imp_CoTaskMemAlloc
0x180019ade  mov     [rdi], rax
0x180019ae1  test    rax, rax
0x180019ae4  jnz     short loc_180019AF0
0x180019ae6  mov     eax, 8007000Eh
0x180019aeb  jmp     loc_180019C3D
0x180019af0  xor     edx, edx; Val
0x180019af2  mov     rcx, rax; void *
0x180019af5  lea     r8d, [rdx+58h]; Size
0x180019af9  call    memset_0
0x180019afe  mov     rax, [rsi]
0x180019b01  mov     edx, r14d
0x180019b04  mov     r8, [rdi]
0x180019b07  mov     rcx, rsi
0x180019b0a  mov     rax, [rax+68h]
0x180019b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b13  mov     esi, eax
0x180019b15  test    eax, eax
0x180019b17  jz      short loc_180019B48
0x180019b19  mov     rcx, [rdi]; pv
0x180019b1c  call    cs:__imp_CoTaskMemFree
0x180019b22  mov     qword ptr [rdi], 0
0x180019b29  mov     eax, 1
0x180019b2e  cmp     esi, 80040206h
0x180019b34  jz      loc_180019C3D
0x180019b3a  cmp     esi, 80070057h
0x180019b40  cmovnz  eax, esi
0x180019b43  jmp     loc_180019C3D
0x180019b48  mov     rcx, [rbp-98h]
0x180019b4f  mov     rax, [rcx+1A8h]
0x180019b56  cmp     rax, qword ptr cs:DMOCATEGORY_VIDEO_ENCODER.Data1
0x180019b5d  jnz     short loc_180019BCA
0x180019b5f  mov     rax, [rcx+1B0h]
0x180019b66  cmp     rax, qword ptr cs:DMOCATEGORY_VIDEO_ENCODER.Data4
0x180019b6d  jnz     short loc_180019BCA
0x180019b6f  xor     edx, edx; Val
0x180019b71  mov     r8d, 80h; Size
0x180019b77  mov     rcx, rbx; void *
0x180019b7a  call    memset_0
0x180019b7f  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x180019b86  movdqu  xmmword ptr [rbx], xmm0
0x180019b8a  mov     rax, [rdi]
0x180019b8d  mov     rcx, [rax+50h]
0x180019b91  test    rcx, rcx
0x180019b94  jz      loc_180019C34
0x180019b9a  cmp     dword ptr [rax+48h], 0
0x180019b9e  jbe     loc_180019C34
0x180019ba4  mov     eax, [rcx+34h]
0x180019ba7  mov     [rbx+14h], eax
0x180019baa  mov     eax, [rcx+38h]
0x180019bad  mov     [rbx+18h], eax
0x180019bb0  mov     eax, [rcx+34h]
0x180019bb3  mov     [rbx+1Ch], eax
0x180019bb6  mov     eax, [rcx+38h]
0x180019bb9  mov     [rbx+20h], eax
0x180019bbc  mov     eax, [rcx+34h]
0x180019bbf  mov     [rbx+24h], eax
0x180019bc2  mov     eax, [rcx+38h]
0x180019bc5  mov     [rbx+28h], eax
0x180019bc8  jmp     short loc_180019C34
0x180019bca  xorps   xmm0, xmm0
0x180019bcd  xor     eax, eax
0x180019bcf  movups  xmmword ptr [rbx], xmm0
0x180019bd2  movups  xmmword ptr [rbx+10h], xmm0
0x180019bd6  movups  xmmword ptr [rbx+20h], xmm0
0x180019bda  mov     [rbx+30h], eax
0x180019bdd  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x180019be4  movdqu  xmmword ptr [rbx], xmm0
0x180019be8  mov     rax, [rdi]
0x180019beb  mov     rdx, [rax+50h]
0x180019bef  test    rdx, rdx
0x180019bf2  jz      short loc_180019C34
0x180019bf4  cmp     dword ptr [rax+48h], 0
0x180019bf8  jbe     short loc_180019C34
0x180019bfa  movzx   eax, word ptr [rdx+2]
0x180019bfe  mov     ecx, 1
0x180019c03  mov     [rbx+10h], eax
0x180019c06  movzx   eax, word ptr [rdx+2]
0x180019c0a  mov     [rbx+14h], eax
0x180019c0d  mov     [rbx+18h], ecx
0x180019c10  movzx   eax, word ptr [rdx+0Eh]
0x180019c14  mov     [rbx+1Ch], eax
0x180019c17  movzx   eax, word ptr [rdx+0Eh]
0x180019c1b  mov     [rbx+20h], eax
0x180019c1e  mov     dword ptr [rbx+24h], 8
0x180019c25  mov     eax, [rdx+4]
0x180019c28  mov     [rbx+28h], eax
0x180019c2b  mov     eax, [rdx+4]
0x180019c2e  mov     [rbx+2Ch], eax
0x180019c31  mov     [rbx+30h], ecx
0x180019c34  xor     eax, eax
0x180019c36  jmp     short loc_180019C3D
0x180019c38  mov     eax, 80004003h
0x180019c3d  mov     rcx, [rsp+68h+var_30]
0x180019c42  xor     rcx, rsp; StackCookie
0x180019c45  call    __security_check_cookie
0x180019c4a  add     rsp, 40h
0x180019c4e  pop     r14
0x180019c50  pop     rdi
0x180019c51  pop     rsi
0x180019c52  pop     rbp
0x180019c53  pop     rbx
0x180019c54  retn
```
