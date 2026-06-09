# CMStream::ConvertILB(ulong,_ULARGE_INTEGER)

- ea: `0x18005bd84`
- end: `0x18005bf20`
- name: `?ConvertILB@CMStream@@AEAAJKT_ULARGE_INTEGER@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CMStream *__hidden this, unsigned int, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005bfa4`

## callees

- `0x180034570`
- `0x180043100`
- `0x18005bd84`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf0a`

## pseudocode

```c
__int64 __fastcall CMStream::ConvertILB(CMStream *this, unsigned int a2, union _ULARGE_INTEGER a3)
{
  __int64 v4; // r14
  unsigned int v5; // ecx
  int Buffer; // esi
  __int64 v8; // r9
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  void *pv; // [rsp+30h] [rbp-28h] BYREF
  int v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  v4 = a2;
  v5 = *((unsigned __int16 *)this + 712);
  pv = 0;
  LODWORD(v17) = 0;
  Buffer = GetBuffer(v5, v5, (unsigned __int8 **)&pv, (unsigned int *)&v17);
  if ( Buffer >= 0 )
  {
    memset_0(pv, 0, *((unsigned __int16 *)this + 712));
    v8 = *((unsigned __int16 *)this + 712);
    if ( ((v8 - 1) & a3.QuadPart) == 0
      || ((v9 = *(_QWORD *)this, LODWORD(v17) = v8 - (a3.LowPart & (v8 - 1)), !v9)
        ? (v10 = 0)
        : (v10 = (_QWORD *)(v9 + *(_QWORD *)NtCurrentTeb()->ReservedForOle)),
          Buffer = (*(__int64 (__fastcall **)(_QWORD, union _ULARGE_INTEGER, void *))(*(_QWORD *)*v10 + 32LL))(
                     *v10,
                     a3,
                     pv),
          Buffer >= 0) )
    {
      v11 = *(_QWORD *)this;
      v16 = 0;
      v17 = 0;
      if ( v11 )
        v12 = (_QWORD *)(v11 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v12 = 0;
      Buffer = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, _QWORD, int *))(*(_QWORD *)*v12 + 24LL))(
                 *v12,
                 v17,
                 pv,
                 *((unsigned __int16 *)this + 712),
                 &v16);
      if ( Buffer >= 0 )
      {
        if ( *(_QWORD *)this )
          v13 = (_QWORD *)(*(_QWORD *)this + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
        else
          v13 = 0;
        Buffer = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, _QWORD, int *))(*(_QWORD *)*v13 + 32LL))(
                   *v13,
                   v4 << *((_BYTE *)this + 1426),
                   pv,
                   *((unsigned __int16 *)this + 712),
                   &v16);
      }
    }
  }
  CoTaskMemFree(pv);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x18005bd84  mov     rax, rsp
0x18005bd87  mov     [rax+10h], rbx
0x18005bd8b  push    rsi
0x18005bd8c  push    rdi
0x18005bd8d  push    r14
0x18005bd8f  sub     rsp, 40h
0x18005bd93  mov     rdi, rcx
0x18005bd96  mov     r14d, edx
0x18005bd99  movzx   ecx, word ptr [rcx+590h]; unsigned int
0x18005bda0  lea     r9, [rax+20h]; unsigned int *
0x18005bda4  mov     rbx, r8
0x18005bda7  mov     qword ptr [rax-28h], 0
0x18005bdaf  mov     edx, ecx; unsigned int
0x18005bdb1  mov     dword ptr [rax+20h], 0
0x18005bdb8  lea     r8, [rax-28h]; unsigned __int8 **
0x18005bdbc  call    ?GetBuffer@@YAJKKPEAPEAEPEAK@Z; GetBuffer(ulong,ulong,uchar * *,ulong *)
0x18005bdc1  mov     esi, eax
0x18005bdc3  test    eax, eax
0x18005bdc5  js      loc_18005BF05
0x18005bdcb  movzx   r8d, word ptr [rdi+590h]; Size
0x18005bdd3  xor     edx, edx; Val
0x18005bdd5  mov     rcx, [rsp+58h+pv]; void *
0x18005bdda  call    memset_0
0x18005bddf  movzx   r9d, word ptr [rdi+590h]
0x18005bde7  lea     rax, [r9-1]
0x18005bdeb  test    rbx, rax
0x18005bdee  jz      short loc_18005BE4B
0x18005bdf0  mov     rdx, [rdi]
0x18005bdf3  lea     eax, [r9-1]
0x18005bdf7  and     eax, ebx
0x18005bdf9  sub     r9d, eax
0x18005bdfc  mov     dword ptr [rsp+58h+arg_18], r9d
0x18005be01  test    rdx, rdx
0x18005be04  jz      short loc_18005BE1E
0x18005be06  mov     rax, gs:30h
0x18005be0f  mov     rcx, [rax+1758h]
0x18005be16  mov     rcx, [rcx]
0x18005be19  add     rcx, rdx
0x18005be1c  jmp     short loc_18005BE20
0x18005be1e  xor     ecx, ecx
0x18005be20  mov     rcx, [rcx]
0x18005be23  lea     rdx, [rsp+58h+arg_18]
0x18005be28  mov     r8, [rsp+58h+pv]
0x18005be2d  mov     [rsp+58h+var_38], rdx
0x18005be32  mov     rdx, rbx
0x18005be35  mov     rax, [rcx]
0x18005be38  mov     rax, [rax+20h]
0x18005be3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be41  mov     esi, eax
0x18005be43  test    eax, eax
0x18005be45  js      loc_18005BF05
0x18005be4b  mov     rdx, [rdi]
0x18005be4e  mov     [rsp+58h+arg_0], 0
0x18005be56  mov     [rsp+58h+arg_18], 0
0x18005be5f  test    rdx, rdx
0x18005be62  jz      short loc_18005BE7C
0x18005be64  mov     rax, gs:30h
0x18005be6d  mov     rcx, [rax+1758h]
0x18005be74  mov     rcx, [rcx]
0x18005be77  add     rcx, rdx
0x18005be7a  jmp     short loc_18005BE7E
0x18005be7c  xor     ecx, ecx
0x18005be7e  mov     rcx, [rcx]
0x18005be81  lea     rdx, [rsp+58h+arg_0]
0x18005be86  movzx   r9d, word ptr [rdi+590h]
0x18005be8e  mov     r8, [rsp+58h+pv]
0x18005be93  mov     [rsp+58h+var_38], rdx
0x18005be98  mov     rax, [rcx]
0x18005be9b  mov     rdx, [rsp+58h+arg_18]
0x18005bea0  mov     rax, [rax+18h]
0x18005bea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bea9  mov     esi, eax
0x18005beab  test    eax, eax
0x18005bead  js      short loc_18005BF05
0x18005beaf  mov     cl, [rdi+592h]
0x18005beb5  mov     rdx, r14
0x18005beb8  mov     r8, [rdi]
0x18005bebb  shl     rdx, cl
0x18005bebe  test    r8, r8
0x18005bec1  jz      short loc_18005BEDB
0x18005bec3  mov     rax, gs:30h
0x18005becc  mov     rcx, [rax+1758h]
0x18005bed3  mov     rcx, [rcx]
0x18005bed6  add     rcx, r8
0x18005bed9  jmp     short loc_18005BEDD
0x18005bedb  xor     ecx, ecx
0x18005bedd  mov     rcx, [rcx]
0x18005bee0  lea     r8, [rsp+58h+arg_0]
0x18005bee5  movzx   r9d, word ptr [rdi+590h]
0x18005beed  mov     [rsp+58h+var_38], r8
0x18005bef2  mov     r8, [rsp+58h+pv]
0x18005bef7  mov     rax, [rcx]
0x18005befa  mov     rax, [rax+20h]
0x18005befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf03  mov     esi, eax
0x18005bf05  mov     rcx, [rsp+58h+pv]; pv
0x18005bf0a  call    cs:__imp_CoTaskMemFree
0x18005bf10  mov     rbx, [rsp+58h+arg_8]
0x18005bf15  mov     eax, esi
0x18005bf17  add     rsp, 40h
0x18005bf1b  pop     r14
0x18005bf1d  pop     rdi
0x18005bf1e  pop     rsi
0x18005bf1f  retn
```
