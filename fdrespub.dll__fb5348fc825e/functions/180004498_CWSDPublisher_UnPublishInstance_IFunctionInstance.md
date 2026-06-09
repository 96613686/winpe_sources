# CWSDPublisher::UnPublishInstance(IFunctionInstance *)

- ea: `0x180004498`
- end: `0x180004638`
- name: `?UnPublishInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this, struct IFunctionInstance *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800036b0`
- `0x180004640`

## callees

- `0x180001014`
- `0x180001020`
- `0x180002a3c`
- `0x180002ad0`
- `0x180003404`
- `0x180004348`
- `0x180004498`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000461d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000461d`

## string_xrefs

- `0x1800045cf`: `IWSDDeviceHost::RemoveDynamicService`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::UnPublishInstance(CWSDPublisher *this, struct IFunctionInstance *a2)
{
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rcx
  int v15; // eax
  const struct _EVENT_DESCRIPTOR *v16; // rcx
  struct INSTANCE_INFO *InstanceInfo; // rax
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  lpVtbl = a2->lpVtbl;
  pv = 0;
  v5 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))lpVtbl->GetID)(a2, &pv);
  if ( !v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)pv + v6) );
    v7 = (unsigned int)(v6 + 6);
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v7, 2u));
    v9 = v8;
    if ( v8 )
    {
      if ( v7 )
      {
        if ( v7 <= 0x7FFFFFFF )
        {
          v10 = 2147483646;
          v11 = L"fdid:";
          v12 = v7;
          v13 = v9;
          do
          {
            if ( !v10 )
              break;
            if ( !*v11 )
              break;
            *v13++ = *v11++;
            --v10;
            --v12;
          }
          while ( v12 );
          v14 = v13 - 1;
          v5 = v12 == 0 ? 0x8007007A : 0;
          if ( v12 )
            v14 = v13;
          *v14 = 0;
          if ( v12 )
            v5 = StringCchCatW(v9, v7, (unsigned __int16 *)pv);
        }
        else
        {
          v5 = -2147024809;
          *v8 = 0;
        }
      }
      else
      {
        v5 = -2147024809;
      }
      if ( !v5 )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 9) + 96LL))(
                *((_QWORD *)this + 9),
                v9);
        v5 = v15;
        if ( v15 )
        {
          LogError(v16, v15, L"IWSDDeviceHost::RemoveDynamicService", 1520);
        }
        else
        {
          InstanceInfo = CWSDPublisher::FindInstanceInfo(this, (const unsigned __int16 *)pv);
          if ( InstanceInfo )
          {
            *((_DWORD *)this + 23) -= *((_DWORD *)InstanceInfo + 6);
            CWSDPublisher::FreeInstanceInfo(this, (const unsigned __int16 *)pv);
          }
        }
      }
      operator delete[](v9);
    }
    else
    {
      v5 = -2147024882;
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x180004498  mov     [rsp+arg_0], rbx
0x18000449d  mov     [rsp+arg_10], rbp
0x1800044a2  push    rsi
0x1800044a3  push    rdi
0x1800044a4  push    r14
0x1800044a6  sub     rsp, 30h
0x1800044aa  xor     r14d, r14d
0x1800044ad  mov     r8, rdx
0x1800044b0  mov     rbp, rcx
0x1800044b3  test    rdx, rdx
0x1800044b6  jnz     short loc_1800044C2
0x1800044b8  mov     eax, 80070057h
0x1800044bd  jmp     loc_180004625
0x1800044c2  mov     rax, [rdx]
0x1800044c5  mov     rcx, r8
0x1800044c8  lea     rdx, [rsp+48h+pv]
0x1800044cd  mov     [rsp+48h+pv], r14
0x1800044d2  mov     rax, [rax+20h]
0x1800044d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044db  mov     ebx, eax
0x1800044dd  test    eax, eax
0x1800044df  jnz     loc_180004613
0x1800044e5  mov     rcx, [rsp+48h+pv]
0x1800044ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800044ee  mov     rax, r8
0x1800044f1  inc     rax
0x1800044f4  cmp     [rcx+rax*2], r14w
0x1800044f9  jnz     short loc_1800044F1
0x1800044fb  lea     edi, [rax+6]
0x1800044fe  mov     eax, 2
0x180004503  mul     rdi
0x180004506  cmovb   rax, r8
0x18000450a  mov     rcx, rax; unsigned __int64
0x18000450d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180004512  mov     rsi, rax
0x180004515  test    rax, rax
0x180004518  jz      loc_18000460E
0x18000451e  test    rdi, rdi
0x180004521  jz      short loc_18000459E
0x180004523  cmp     rdi, 7FFFFFFFh
0x18000452a  jbe     short loc_180004533
0x18000452c  mov     ebx, 80070057h
0x180004531  jmp     short loc_1800045A8
0x180004533  mov     eax, 7FFFFFFEh
0x180004538  lea     rcx, aFdid; "fdid:"
0x18000453f  mov     rdx, rdi
0x180004542  mov     r8, rsi
0x180004545  test    rax, rax
0x180004548  jz      short loc_180004569
0x18000454a  movzx   r9d, word ptr [rcx]
0x18000454e  test    r9w, r9w
0x180004552  jz      short loc_180004569
0x180004554  mov     [r8], r9w
0x180004558  add     rcx, 2
0x18000455c  add     r8, 2
0x180004560  dec     rax
0x180004563  sub     rdx, 1
0x180004567  jnz     short loc_180004545
0x180004569  mov     rax, rdx
0x18000456c  lea     rcx, [r8-2]
0x180004570  neg     rax
0x180004573  sbb     ebx, ebx
0x180004575  not     ebx
0x180004577  and     ebx, 8007007Ah
0x18000457d  test    rdx, rdx
0x180004580  cmovnz  rcx, r8
0x180004584  mov     [rcx], r14w
0x180004588  jz      short loc_1800045AC
0x18000458a  mov     r8, [rsp+48h+pv]; unsigned __int16 *
0x18000458f  mov     rdx, rdi; unsigned __int64
0x180004592  mov     rcx, rsi; unsigned __int16 *
0x180004595  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000459a  mov     ebx, eax
0x18000459c  jmp     short loc_1800045AC
0x18000459e  mov     ebx, 80070057h
0x1800045a3  test    rdi, rdi
0x1800045a6  jz      short loc_1800045AC
0x1800045a8  mov     [rax], r14w
0x1800045ac  test    ebx, ebx
0x1800045ae  jnz     short loc_180004604
0x1800045b0  mov     rcx, [rbp+48h]
0x1800045b4  mov     rdx, rsi
0x1800045b7  mov     rax, [rcx]
0x1800045ba  mov     rax, [rax+60h]
0x1800045be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c3  mov     ebx, eax
0x1800045c5  test    eax, eax
0x1800045c7  jz      short loc_1800045DF
0x1800045c9  mov     r9d, 5F0h; unsigned int
0x1800045cf  lea     r8, aIwsddevicehost_3; "IWSDDeviceHost::RemoveDynamicService"
0x1800045d6  mov     edx, eax; int
0x1800045d8  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x1800045dd  jmp     short loc_180004604
0x1800045df  mov     rdx, [rsp+48h+pv]; unsigned __int16 *
0x1800045e4  mov     rcx, rbp; this
0x1800045e7  call    ?FindInstanceInfo@CWSDPublisher@@IEAAPEAUINSTANCE_INFO@@PEBG@Z; CWSDPublisher::FindInstanceInfo(ushort const *)
0x1800045ec  test    rax, rax
0x1800045ef  jz      short loc_180004604
0x1800045f1  mov     eax, [rax+18h]
0x1800045f4  mov     rcx, rbp; this
0x1800045f7  sub     [rbp+5Ch], eax
0x1800045fa  mov     rdx, [rsp+48h+pv]; unsigned __int16 *
0x1800045ff  call    ?FreeInstanceInfo@CWSDPublisher@@IEAAJPEBG@Z; CWSDPublisher::FreeInstanceInfo(ushort const *)
0x180004604  mov     rcx, rsi; Block
0x180004607  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000460c  jmp     short loc_180004613
0x18000460e  mov     ebx, 8007000Eh
0x180004613  mov     rcx, [rsp+48h+pv]; pv
0x180004618  test    rcx, rcx
0x18000461b  jz      short loc_180004623
0x18000461d  call    cs:__imp_CoTaskMemFree
0x180004623  mov     eax, ebx
0x180004625  mov     rbx, [rsp+48h+arg_0]
0x18000462a  mov     rbp, [rsp+48h+arg_10]
0x18000462f  add     rsp, 30h
0x180004633  pop     r14
0x180004635  pop     rdi
0x180004636  pop     rsi
0x180004637  retn
```
