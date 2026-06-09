# CKsOutputPin::GetFormat(_AMMediaType * *)

- ea: `0x10017af0`
- end: `0x10017b7c`
- name: `?GetFormat@CKsOutputPin@@UAGJPAPAU_AMMediaType@@@Z`
- size: `140`
- prototype: `int __userpurge@<eax>(struct _AMMediaType *@<edi>, const struct _AMMediaType *@<esi>, CKsOutputPin *this, struct _AMMediaType **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x10017af0`
- `0x1002d510`
- `0x100302a7`
- `0x100302fd`
- `0x1003b5e4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10017af8`
- `ole32!CoTaskMemAlloc` at `0x10017af8`

## pseudocode

```c
int __userpurge CKsOutputPin::GetFormat@<eax>(
        struct _AMMediaType *a1@<edi>,
        const struct _AMMediaType *a2@<esi>,
        CKsOutputPin *this,
        struct _AMMediaType **a4)
{
  struct _AMMediaType *v4; // eax
  int v6; // esi
  struct _AMMediaType *v7; // [esp-8h] [ebp-Ch]

  v4 = (struct _AMMediaType *)CoTaskMemAlloc(0x48u);
  *a4 = v4;
  if ( !v4 )
    return -2147024882;
  v7 = a1;
  v6 = 0;
  memset((void *)v4, 0, sizeof(struct _AMMediaType));
  if ( *(_DWORD *)&this->m_mt.majortype.Data2 )
  {
    CopyMediaType(a1, a2);
    if ( !this[-1].m_IoCriticalSection.m_CritSec.OwningThread || (*a4)->cbFormat )
      return v6;
    v6 = -2147024882;
    goto LABEL_8;
  }
  v6 = (*(int (__thiscall **)(unsigned __int8 *, _DWORD, _DWORD))(*((_DWORD *)&this[-1].m_CurrentInterface.Alignment + 3)
                                                                + 52))(
         &this[-1].m_CurrentInterface.Set.Data4[4],
         0,
         *a4);
  if ( v6 < 0 )
LABEL_8:
    DeleteMediaType(v7);
  return v6;
}

```

## disassembly

```asm
0x10017af0  mov     edi, edi
0x10017af2  push    ebp
0x10017af3  mov     ebp, esp
0x10017af5  push    ebx
0x10017af6  push    48h ; 'H'; cb
0x10017af8  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10017afe  mov     ebx, [ebp+arg_4]
0x10017b01  mov     [ebx], eax
0x10017b03  test    eax, eax
0x10017b05  jnz     short loc_10017B0E
0x10017b07  mov     eax, 8007000Eh
0x10017b0c  jmp     short loc_10017B77
0x10017b0e  push    esi; const struct _AMMediaType *
0x10017b0f  push    edi; struct _AMMediaType *
0x10017b10  push    48h ; 'H'; Size
0x10017b12  xor     esi, esi
0x10017b14  push    esi; Val
0x10017b15  push    eax; void *
0x10017b16  call    _memset
0x10017b1b  mov     edi, [ebp+this]
0x10017b1e  add     esp, 0Ch
0x10017b21  cmp     [edi+38h], esi
0x10017b24  jz      short loc_10017B49
0x10017b26  mov     ecx, [ebx]
0x10017b28  lea     edx, [edi-0F8h]
0x10017b2e  call    ?CopyMediaType@@YGJPAU_AMMediaType@@PBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x10017b33  cmp     [edi-0B8h], esi
0x10017b39  jz      short loc_10017B73
0x10017b3b  mov     eax, [ebx]
0x10017b3d  cmp     [eax+40h], esi
0x10017b40  jnz     short loc_10017B73
0x10017b42  mov     esi, 8007000Eh
0x10017b47  jmp     short loc_10017B6C
0x10017b49  mov     eax, [edi-12Ch]
0x10017b4f  push    dword ptr [ebx]
0x10017b51  push    0
0x10017b53  mov     esi, [eax+34h]
0x10017b56  mov     ecx, esi; this
0x10017b58  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10017b5e  lea     ecx, [edi-12Ch]
0x10017b64  call    esi
0x10017b66  mov     esi, eax
0x10017b68  test    esi, esi
0x10017b6a  jns     short loc_10017B73
0x10017b6c  mov     ecx, [ebx]
0x10017b6e  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x10017b73  pop     edi
0x10017b74  mov     eax, esi
0x10017b76  pop     esi
0x10017b77  pop     ebx
0x10017b78  pop     ebp
0x10017b79  retn    8
```
