# DriverSecurityContext::CopyTo(CACSecurityContext *,SecurityContextRetrievalState *)

- ea: `0x14000e834`
- end: `0x14000e9a0`
- name: `?CopyTo@DriverSecurityContext@@QEBAXPEAVCACSecurityContext@@PEAUSecurityContextRetrievalState@@@Z`
- size: `364`
- prototype: `void __fastcall(DriverSecurityContext *__hidden this, struct CACSecurityContext *, struct SecurityContextRetrievalState *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140006808`

## callees

- `0x140001c04`
- `0x14000770c`
- `0x14000e834`
- `0x14000eb60`
- `0x140024cc0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14000e8aa`
- `ntoskrnl!ProbeForWrite` at `0x14000e8c2`
- `ntoskrnl!ProbeForWrite` at `0x14000e8aa`
- `ntoskrnl!ProbeForWrite` at `0x14000e8c2`

## pseudocode

```c
void __fastcall DriverSecurityContext::CopyTo(
        DriverSecurityContext *this,
        struct CACSecurityContext *a2,
        struct SecurityContextRetrievalState *a3)
{
  size_t v4; // r14
  unsigned int v6; // eax
  unsigned int v8; // r15d
  unsigned __int64 v9; // rbp
  wchar_t *v10; // r8
  unsigned int v11; // ecx
  unsigned int v12; // edx
  volatile void *v13; // r12
  volatile void *v14; // r13
  __int64 v15; // rdx
  int v16; // eax
  wchar_t *v17; // [rsp+70h] [rbp+8h]

  *((_DWORD *)a3 + 3) = -1073741823;
  v4 = *((unsigned int *)this + 10);
  v6 = *((_DWORD *)a2 + 10);
  v8 = *((_DWORD *)this + 9);
  v9 = *((unsigned int *)this + 11);
  v10 = (wchar_t *)*((_QWORD *)a2 + 2);
  v11 = *((_DWORD *)a2 + 9);
  v12 = *((_DWORD *)a2 + 11);
  v13 = (volatile void *)*((_QWORD *)a2 + 1);
  v14 = *(volatile void **)a2;
  v17 = v10;
  *(_DWORD *)a3 = v4;
  *((_DWORD *)a3 + 1) = v8;
  *((_DWORD *)a3 + 2) = v9;
  if ( v6 < (unsigned int)v4 || v11 < v8 || v12 < (unsigned int)v9 )
  {
    *((_DWORD *)a3 + 3) = -1073741789;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
    }
  }
  else
  {
    ProbeForWrite(v14, v8, 1u);
    ProbeForWrite(v13, (unsigned int)v4, 1u);
    ACProbeArrayElementsForWrite(v17, v15, (unsigned int)v9);
    if ( v8 )
    {
      memmove((void *)v14, *(const void **)this, v8);
      *((_DWORD *)a2 + 9) = v8;
    }
    if ( (_DWORD)v4 )
    {
      memmove((void *)v13, *((const void **)this + 1), v4);
      *((_DWORD *)a2 + 10) = v4;
    }
    if ( (_DWORD)v9
      && (*((_DWORD *)a2 + 11) = v9, v16 = StringCchCopyW(v17, v9, *((const wchar_t **)this + 2)), v16 < 0) )
    {
      *((_DWORD *)a3 + 3) = v16;
    }
    else
    {
      *((_DWORD *)a2 + 6) = *((_DWORD *)this + 6);
      *((_DWORD *)a2 + 12) = *((_DWORD *)this + 12);
      *((_DWORD *)a2 + 14) = *((_DWORD *)this + 14);
      *((_DWORD *)a2 + 8) = *((_DWORD *)this + 8);
      *((_DWORD *)a2 + 7) = *((_DWORD *)this + 7);
      *((_DWORD *)a2 + 15) = *((_DWORD *)this + 15);
      *((_DWORD *)a3 + 3) = 0;
    }
  }
}

```

## disassembly

```asm
0x14000e834  push    rbx
0x14000e836  push    rbp
0x14000e837  push    rsi
0x14000e838  push    rdi
0x14000e839  push    r12
0x14000e83b  push    r13
0x14000e83d  push    r14
0x14000e83f  push    r15
0x14000e841  sub     rsp, 28h
0x14000e845  mov     dword ptr [r8+0Ch], 0C0000001h
0x14000e84d  mov     rbx, rdx
0x14000e850  mov     r14d, [rcx+28h]
0x14000e854  mov     rsi, r8
0x14000e857  mov     eax, [rdx+28h]
0x14000e85a  mov     rdi, rcx
0x14000e85d  mov     r15d, [rcx+24h]
0x14000e861  mov     ebp, [rcx+2Ch]
0x14000e864  mov     r8, [rbx+10h]
0x14000e868  mov     ecx, [rdx+24h]
0x14000e86b  mov     edx, [rdx+2Ch]
0x14000e86e  mov     r12, [rbx+8]
0x14000e872  mov     r13, [rbx]
0x14000e875  mov     [rsp+68h+arg_0], r8
0x14000e87a  mov     [rsi], r14d
0x14000e87d  mov     [rsi+4], r15d
0x14000e881  mov     [rsi+8], ebp
0x14000e884  cmp     eax, r14d
0x14000e887  jb      loc_14000E958
0x14000e88d  cmp     ecx, r15d
0x14000e890  jb      loc_14000E958
0x14000e896  cmp     edx, ebp
0x14000e898  jb      loc_14000E958
0x14000e89e  mov     edx, r15d; Length
0x14000e8a1  mov     r8d, 1; Alignment
0x14000e8a7  mov     rcx, r13; Address
0x14000e8aa  call    cs:__imp_ProbeForWrite
0x14000e8b1  nop     dword ptr [rax+rax+00h]
0x14000e8b6  mov     edx, r14d; Length
0x14000e8b9  mov     r8d, 1; Alignment
0x14000e8bf  mov     rcx, r12; Address
0x14000e8c2  call    cs:__imp_ProbeForWrite
0x14000e8c9  nop     dword ptr [rax+rax+00h]
0x14000e8ce  mov     rcx, [rsp+68h+arg_0]; void *
0x14000e8d3  mov     r8d, ebp; unsigned int
0x14000e8d6  call    ?ACProbeArrayElementsForWrite@@YAXPEAXKK@Z; ACProbeArrayElementsForWrite(void *,ulong,ulong)
0x14000e8db  test    r15d, r15d
0x14000e8de  jz      short loc_14000E8F2
0x14000e8e0  mov     rdx, [rdi]; Src
0x14000e8e3  mov     r8d, r15d; Size
0x14000e8e6  mov     rcx, r13; void *
0x14000e8e9  call    memmove
0x14000e8ee  mov     [rbx+24h], r15d
0x14000e8f2  test    r14d, r14d
0x14000e8f5  jz      short loc_14000E90A
0x14000e8f7  mov     rdx, [rdi+8]; Src
0x14000e8fb  mov     r8, r14; Size
0x14000e8fe  mov     rcx, r12; void *
0x14000e901  call    memmove
0x14000e906  mov     [rbx+28h], r14d
0x14000e90a  test    ebp, ebp
0x14000e90c  jz      short loc_14000E92B
0x14000e90e  mov     rcx, [rsp+68h+arg_0]; wchar_t *
0x14000e913  mov     rdx, rbp; unsigned __int64
0x14000e916  mov     [rbx+2Ch], ebp
0x14000e919  mov     r8, [rdi+10h]; wchar_t *
0x14000e91d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000e922  test    eax, eax
0x14000e924  jns     short loc_14000E92B
0x14000e926  mov     [rsi+0Ch], eax
0x14000e929  jmp     short loc_14000E98E
0x14000e92b  mov     eax, [rdi+18h]
0x14000e92e  mov     [rbx+18h], eax
0x14000e931  mov     eax, [rdi+30h]
0x14000e934  mov     [rbx+30h], eax
0x14000e937  mov     eax, [rdi+38h]
0x14000e93a  mov     [rbx+38h], eax
0x14000e93d  mov     eax, [rdi+20h]
0x14000e940  mov     [rbx+20h], eax
0x14000e943  mov     eax, [rdi+1Ch]
0x14000e946  mov     [rbx+1Ch], eax
0x14000e949  mov     eax, [rdi+3Ch]
0x14000e94c  mov     [rbx+3Ch], eax
0x14000e94f  mov     dword ptr [rsi+0Ch], 0
0x14000e956  jmp     short loc_14000E98E
0x14000e958  mov     dword ptr [rsi+0Ch], 0C0000023h
0x14000e95f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e966  lea     rax, WPP_GLOBAL_Control
0x14000e96d  cmp     rcx, rax
0x14000e970  jz      short loc_14000E98E
0x14000e972  mov     eax, [rcx+6Ch]
0x14000e975  test    al, 1
0x14000e977  jz      short loc_14000E98E
0x14000e979  mov     rcx, [rcx+58h]
0x14000e97d  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e984  mov     edx, 0Fh
0x14000e989  call    WPP_SF_
0x14000e98e  add     rsp, 28h
0x14000e992  pop     r15
0x14000e994  pop     r14
0x14000e996  pop     r13
0x14000e998  pop     r12
0x14000e99a  pop     rdi
0x14000e99b  pop     rsi
0x14000e99c  pop     rbp
0x14000e99d  pop     rbx
0x14000e99e  retn
```
