# MakeCLSIDRegPath(_GUID const &,ushort * const)

- ea: `0x18000fdd0`
- end: `0x18000fe76`
- name: `?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z`
- size: `166`
- prototype: `int(const struct _GUID *, unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fc50`
- `0x18000ffb4`

## callees

- `0x18000ff28`

## string_xrefs

- `0x18000fe4d`: `CLSID\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
__int64 __fastcall MakeCLSIDRegPath(const struct _GUID *a1, unsigned __int16 *const a2)
{
  int Data2; // [rsp+20h] [rbp-78h]
  int Data3; // [rsp+28h] [rbp-70h]
  int v5; // [rsp+30h] [rbp-68h]
  int v6; // [rsp+38h] [rbp-60h]
  int v7; // [rsp+40h] [rbp-58h]
  int v8; // [rsp+48h] [rbp-50h]
  int v9; // [rsp+50h] [rbp-48h]
  int v10; // [rsp+58h] [rbp-40h]
  int v11; // [rsp+60h] [rbp-38h]
  int v12; // [rsp+68h] [rbp-30h]

  v12 = CLSID_CMP3DecMediaObject.Data4[7];
  v11 = CLSID_CMP3DecMediaObject.Data4[6];
  v10 = CLSID_CMP3DecMediaObject.Data4[5];
  v9 = CLSID_CMP3DecMediaObject.Data4[4];
  v8 = CLSID_CMP3DecMediaObject.Data4[3];
  v7 = CLSID_CMP3DecMediaObject.Data4[2];
  v6 = CLSID_CMP3DecMediaObject.Data4[1];
  v5 = CLSID_CMP3DecMediaObject.Data4[0];
  Data3 = CLSID_CMP3DecMediaObject.Data3;
  Data2 = CLSID_CMP3DecMediaObject.Data2;
  return StringCchPrintfW(
           a2,
           0x50u,
           L"CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
           CLSID_CMP3DecMediaObject.Data1,
           Data2,
           Data3,
           v5,
           v6,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12);
}

```

## disassembly

```asm
0x18000fdd0  push    rbx
0x18000fdd2  push    rbp
0x18000fdd3  push    rsi
0x18000fdd4  push    rdi
0x18000fdd5  sub     rsp, 78h
0x18000fdd9  movzx   r9d, cs:CLSID_CMP3DecMediaObject.Data4+2
0x18000fde1  mov     rbp, rdx
0x18000fde4  movzx   r8d, cs:CLSID_CMP3DecMediaObject.Data4+1
0x18000fdec  movzx   edx, cs:CLSID_CMP3DecMediaObject.Data4
0x18000fdf3  movzx   ecx, cs:CLSID_CMP3DecMediaObject.Data3
0x18000fdfa  movzx   esi, cs:CLSID_CMP3DecMediaObject.Data4+7
0x18000fe01  movzx   edi, cs:CLSID_CMP3DecMediaObject.Data4+6
0x18000fe08  movzx   ebx, cs:CLSID_CMP3DecMediaObject.Data4+5
0x18000fe0f  movzx   r11d, cs:CLSID_CMP3DecMediaObject.Data4+4
0x18000fe17  movzx   r10d, cs:CLSID_CMP3DecMediaObject.Data4+3
0x18000fe1f  movzx   eax, cs:CLSID_CMP3DecMediaObject.Data2
0x18000fe26  mov     [rsp+98h+var_30], esi
0x18000fe2a  mov     [rsp+98h+var_38], edi
0x18000fe2e  mov     [rsp+98h+var_40], ebx
0x18000fe32  mov     [rsp+98h+var_48], r11d
0x18000fe37  mov     [rsp+98h+var_50], r10d
0x18000fe3c  mov     [rsp+98h+var_58], r9d
0x18000fe41  mov     r9d, cs:CLSID_CMP3DecMediaObject.Data1
0x18000fe48  mov     [rsp+98h+var_60], r8d
0x18000fe4d  lea     r8, aClsid08x04x04x; "CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x18000fe54  mov     [rsp+98h+var_68], edx
0x18000fe58  mov     edx, 50h ; 'P'; unsigned __int64
0x18000fe5d  mov     [rsp+98h+var_70], ecx
0x18000fe61  mov     rcx, rbp; unsigned __int16 *
0x18000fe64  mov     [rsp+98h+var_78], eax
0x18000fe68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fe6d  add     rsp, 78h
0x18000fe71  pop     rdi
0x18000fe72  pop     rsi
0x18000fe73  pop     rbp
0x18000fe74  pop     rbx
0x18000fe75  retn
```
